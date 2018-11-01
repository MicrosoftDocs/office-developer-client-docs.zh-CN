---
title: 步骤 2：初始化主列表框
TOCTitle: 'Step 2: Initialize the Main List Box'
ms:assetid: 81e4dcfd-6ee0-b5f9-9ea3-026c38c26bf0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249562(v=office.15)
ms:contentKeyID: 48545967
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3505c2726da3f2f2f01d179c97cde5a1d7b635ba
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869895"
---
# <a name="step-2-initialize-the-main-list-box"></a>步骤 2：初始化主列表框


**适用于**： Access 2013、 Office 2013

## <a name="step-2-initialize-the-main-list-box"></a>步骤 2：初始化主列表框

**声明全局 Record 和 Recordset 对象**

  - 将以下代码插入 Form1 的 (General) (Declarations) 中：
    
    ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
    ```
    
    上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。

**连接到 URL 并填充 lstMain**

  - 将以下代码插入 Form1 的 Form Load 事件处理程序中：
    
    ```vb 
     
    Private Sub Form_Load() 
        Set grec = New Record 
        Set grs = New Recordset 
        grec.Open "", "URL=https://servername/foldername/", , _ 
            adOpenIfExists Or adCreateCollection 
        Set grs = grec.GetChildren 
        While Not grs.EOF 
            lstMain.AddItem grs(0) 
            grs.MoveNext 
        Wend 
    End Sub 
    ```
    
    上面的代码实例化全局 **Record** 和 **Recordset** 对象。 **记录**，grec，打开与指定为**ActiveConnection**的 URL。 如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。 请注意，您应当将"https://servername/foldername/"替换为您的环境中的有效 URL。 **记录**的 grec 子级上打开**Recordset**，grs。 随后，lstMain 将用发布到该 URL 的资源的文件名填充。

