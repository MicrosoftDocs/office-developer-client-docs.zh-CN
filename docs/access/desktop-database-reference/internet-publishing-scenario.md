---
title: Internet 发布方案
TOCTitle: Internet publishing scenario
ms:assetid: 25a3fa8b-86ec-9e72-5e62-bf0d849479b7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249024(v=office.15)
ms:contentKeyID: 48543790
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0f28b14f3eaf6792a74ef0967d698d5a3914955a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291270"
---
# <a name="internet-publishing-scenario"></a>Internet 发布方案

**适用于**：Access 2013、Office 2013

此代码示例演示如何将 ADO 用于 Microsoft OLE DB Provider for Internet Publishing。在此方案中，您将创建一个 Visual Basic 应用程序，该应用程序使用 **Recordset** 、 **Record** 和 **Stream** 对象来显示用 Internet Publishing Provider 发布的资源的内容。

下列步骤是创建该方案所必需的步骤： 

1. 设置 Visual Basic 项目。
2. 初始化主列表框。
3. 填充 "字段" 列表框。
4. 填充 "详细信息" 文本框。

## <a name="step-1-set-up-the-visual-basic-project"></a>步骤 1: 设置 Visual Basic 项目

在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。

### <a name="create-an-ado-project"></a>创建 ADO 项目

1.  在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。

2.  从****“工程”菜单中，选择****“引用”。

3.  选择 " **Microsoft ActiveX 数据对象2.5 库**", 然后单击 **"确定"**。

### <a name="insert-controls-on-the-main-form"></a>在主窗体上插入控件

1.  向 Form1 中添加一个 ListBox 控件。 将其**Name**属性设置为**lstMain**。

2.  向 Form1 中添加另一个 ListBox 控件。 将其**Name**属性设置为**lstDetails**。

3.  向 Form1 中添加一个 TextBox 控件。 将其**Name**属性设置为**txtDetails**。

## <a name="step-2-initialize-the-main-list-box"></a>步骤 2: 初始化主列表框

### <a name="declare-global-record-and-recordset-objects"></a>声明全局 Record 和 Recordset 对象

- 将以下代码插入 Form1 的 (General) (Declarations) 中：
    
   ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
   ```
    
   上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。

### <a name="connect-to-a-url-and-populate-lstmain"></a>连接到 URL 并填充 lstMain

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
    
   上面的代码实例化全局 **Record** 和 **Recordset** 对象。 将使用指定为**ActiveConnection**的 URL 打开该**记录** `grec` 。 如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。 
   
   请注意, 应将`https://servername/foldername/`您的环境中的有效 URL 替换为。 
   
   将在**记录** `grec`的子级上打开**Recordset** `grs` 。 然后, 将使用发布到 URL 的资源的文件名填充 lstMain。

## <a name="step-3-populate-the-fields-list-box"></a>步骤 3: 填充字段列表框

- 将以下代码插入 lstMain 的 Click 事件处理程序中：

   ```vb 
    
    Private Sub lstMain_Click() 
        Dim rec As Record 
        Dim rs As Recordset 
        Set rec = New Record 
        Set rs = New Recordset 
        grs.MoveFirst 
        grs.Move lstMain.ListIndex 
        lstDetails.Clear 
        rec.Open grs 
        Select Case rec.RecordType 
            Case adCollectionRecord: 
                Set rs = rec.GetChildren 
                While Not rs.EOF 
                    lstDetails.AddItem rs(0) 
                    rs.MoveNext 
                Wend 
            Case adSimpleRecord: 
                recFields rec, lstDetails, txtDetails 
                
            Case adStructDoc: 
        End Select 
        
    End Sub 
   ```

   此`rs`代码分别声明和实例化本地**Record**和`rec` **Recordset**对象。

   将与 lstMain 中选定的资源相对应的行作为的当前行`grs`。 然后, "**详细信息**" 列表框`rec`将被清除, 并使用当前`grs`行作为源打开。

   如果资源是集合记录 (由**RecordType**指定), 则会在的子级上打开本地**Recordset** `rs` `rec`。 lstDetails 然后使用的行中的值进行填充`rs`。

   如果资源是简单记录, `recFields`则调用。 有关`recFields`的详细信息, 请参阅下一步。

   如果该资源是结构化文档，则将不实现任何代码。

## <a name="step-4-populate-the-details-text-box"></a>步骤 4: 填充 "详细信息" 文本框

- 创建一个名为`recFields`的新子例程, 并插入以下代码:

   ```vb 
    
    Sub recFields(r As Record, l As ListBox, t As TextBox) 
        Dim f As Field 
        Dim s As Stream 
        Set s = New Stream 
        Dim str As String 
        
        For Each f In r.Fields 
            l.AddItem f.Name & ": " & f.Value 
        Next 
        t.Text = "" 
        If r!RESOURCE_CONTENTCLASS = "text/plain" Then 
            s.Open r, adModeRead, adOpenStreamFromRecord 
            str = s.ReadText(1) 
            s.Position = 0 
            If Asc(Mid(str, 1, 1)) = 63 Then '//63 = "?" 
                s.Charset = "ascii" 
                s.Type = adTypeText 
            End If 
            t.Text = s.ReadText(adReadAll) 
        End If 
    End Sub 
   ```

   此代码使用传递给`recFields`的简单记录的字段和值填充 lstDetails。 如果该资源是文本文件，则将从该资源记录打开文本的 **Stream**。 代码确定字符集是否为 ASCII, 并将**流**内容复制到中`txtDetails`。

