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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708506"
---
# <a name="internet-publishing-scenario"></a>Internet 发布方案

**适用于**： Access 2013、 Office 2013

此代码示例演示如何将 ADO 用于 Microsoft OLE DB Provider for Internet Publishing。在此方案中，您将创建一个 Visual Basic 应用程序，该应用程序使用 **Recordset** 、 **Record** 和 **Stream** 对象来显示用 Internet Publishing Provider 发布的资源的内容。

下列步骤是创建该方案所必需的步骤： 

1. 设置 Visual Basic 项目。
2. 初始化主列表框。
3. 填充 Fields 列表框。
4. 填充 Details 文本框。

## <a name="step-1-set-up-the-visual-basic-project"></a>步骤 1： 设置 Visual Basic 项目

在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。

### <a name="create-an-ado-project"></a>创建 ADO 项目

1.  在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。

2.  从**项目**菜单中，选择**引用**。

3.  选择**Microsoft ActiveX Data Objects 2.5 Library**，，然后单击**确定**。

### <a name="insert-controls-on-the-main-form"></a>在主窗体上插入控件

1.  向 Form1 中添加一个 ListBox 控件。 设置为**lstMain**其**Name**属性。

2.  向 Form1 中添加另一个 ListBox 控件。 设置为**lstDetails**其**Name**属性。

3.  向 Form1 中添加一个 TextBox 控件。 设置为**txtDetails**其**Name**属性。

## <a name="step-2-initialize-the-main-list-box"></a>步骤 2： 初始化主列表框

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
    
   上面的代码实例化全局 **Record** 和 **Recordset** 对象。 **记录**`grec`打开与指定为**ActiveConnection**的 URL。 如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。 
   
   请注意，您应替换`https://servername/foldername/`与环境中的有效 URL。 
   
   **Recordset** `grs` **记录**的子级上打开`grec`。 LstMain 然后填入发布到该 URL 的资源的文件名。

## <a name="step-3-populate-the-fields-list-box"></a>步骤 3： 填充字段列表框

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

   此代码声明并实例化本地**Record**和**Recordset**对象`rec`和`rs`分别。

   LstMain 中所选资源相对应的行进行的当前行`grs`。 然后清除**详细信息**列表框和`rec`打开与当前行的`grs`作为源。

   如果资源是集合记录 （由**RecordType**指定），则本地**Recordset** `rs`上的子级打开`rec`。 然后 lstdetails 将用的行的值`rs`。

   如果资源是一个简单的记录，`recFields`调用。 有关详细信息`recFields`，请参阅下一步。

   如果该资源是结构化文档，则将不实现任何代码。

## <a name="step-4-populate-the-details-text-box"></a>步骤 4： 填充细节文本框

- 创建一个名为的新子例程`recFields`，插入以下代码：

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

   此代码填充 lstDetails 具有字段和简单的记录的值传递到`recFields`。 如果该资源是文本文件，则将从该资源记录打开文本的 **Stream** 。 该代码将确定字符集是否 ASCII，并将复制到的**流**内容`txtDetails`。

