---
title: "mat dialogから親コンポーネントにデータを送る"
date: 2021-09-23T16:37:35+09:00
draft: false
sidebar: false
categories:
  - "development"
tags:
  - "angular"
---

## ダイアログを閉じたときにデータを送る

ダイアログコンポーネント
```
close() {

    this.dialogRef.close(data);
}


constructor(
    public dialogRef: MatDialogRef<MyDialogComponent>,
    @Inject(MAT_DIALOG_DATA) public data: DialogData
  ) { }
```

親コンポーネント
```

openDialog() {

    this.dialogRef = this.myDialog.open(MyDialogComponent, {
      data: {}
    });

    this.dialogRef.afterClosed().subscribe(
        data => console.log("Dialog output:", data)
    );    
}

constructor(
    private myDialog: MatDialog,
) { }

```

## ダイアログを閉じないでデータを送る

ダイアログコンポーネント
```

@Output() submitClicked = new EventEmitter<any>();

sendMessageToParent() {
    const data = 'Your data';
    this.submitClicked.emit(data);
}

```

親コンポーネント
```
private dialogRef
private dialogSubmitSubscription

openDialog() {

    this.dialogRef = this.myDialog.open(MyDialogComponent, {
      data: {}
    });

    this.dialogSubmitSubscription = this.DialogRef.componentInstance.submitClicked
    .subscribe(result => {
      console.log('Got the data!', result);
    });
}

closeDialog() {
    this.dialogSubmitSubscription.unsubscribe();
    this.dialogRef.close()
}

constructor(
    private myDialog: MatDialog,
) { }

```