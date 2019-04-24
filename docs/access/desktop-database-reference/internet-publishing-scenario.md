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
# <a name="internet-publishing-scenario"></a><span data-ttu-id="3da93-102">Internet 发布方案</span><span class="sxs-lookup"><span data-stu-id="3da93-102">Internet publishing scenario</span></span>

<span data-ttu-id="3da93-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3da93-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3da93-p101">此代码示例演示如何将 ADO 用于 Microsoft OLE DB Provider for Internet Publishing。在此方案中，您将创建一个 Visual Basic 应用程序，该应用程序使用 **Recordset** 、 **Record** 和 **Stream** 对象来显示用 Internet Publishing Provider 发布的资源的内容。</span><span class="sxs-lookup"><span data-stu-id="3da93-p101">This code example demonstrates how to use ADO with the Microsoft OLE DB Provider for Internet Publishing. In this scenario, you will create a Visual Basic application that uses **Recordset**, **Record**, and **Stream** objects to display the contents of resources published with the Internet Publishing Provider.</span></span>

<span data-ttu-id="3da93-106">下列步骤是创建该方案所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="3da93-106">The following steps are necessary to create this scenario:</span></span> 

1. <span data-ttu-id="3da93-107">设置 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="3da93-107">Set up the Visual Basic project.</span></span>
2. <span data-ttu-id="3da93-108">初始化主列表框。</span><span class="sxs-lookup"><span data-stu-id="3da93-108">Initialize the Main list box.</span></span>
3. <span data-ttu-id="3da93-109">填充 "字段" 列表框。</span><span class="sxs-lookup"><span data-stu-id="3da93-109">Populate the Fields list box.</span></span>
4. <span data-ttu-id="3da93-110">填充 "详细信息" 文本框。</span><span class="sxs-lookup"><span data-stu-id="3da93-110">Populate the Details text box.</span></span>

## <a name="step-1-set-up-the-visual-basic-project"></a><span data-ttu-id="3da93-111">步骤 1: 设置 Visual Basic 项目</span><span class="sxs-lookup"><span data-stu-id="3da93-111">Step 1: Set up the Visual Basic project</span></span>

<span data-ttu-id="3da93-112">在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。</span><span class="sxs-lookup"><span data-stu-id="3da93-112">In this scenario, it is assumed that you have Microsoft Visual Basic 6.0 or later, ADO 2.5 or later, and the Microsoft OLE DB Provider for Internet Publishing installed on your system.</span></span>

### <a name="create-an-ado-project"></a><span data-ttu-id="3da93-113">创建 ADO 项目</span><span class="sxs-lookup"><span data-stu-id="3da93-113">Create an ADO project</span></span>

1.  <span data-ttu-id="3da93-114">在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。</span><span class="sxs-lookup"><span data-stu-id="3da93-114">In Microsoft Visual Basic, create a new Standard EXE project.</span></span>

2.  <span data-ttu-id="3da93-115">从\*\*\*\*“工程”菜单中，选择\*\*\*\*“引用”。</span><span class="sxs-lookup"><span data-stu-id="3da93-115">From the **Project** menu, choose **References**.</span></span>

3.  <span data-ttu-id="3da93-116">选择 " **Microsoft ActiveX 数据对象2.5 库**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3da93-116">Select **Microsoft ActiveX Data Objects 2.5 Library**, and then click **OK**.</span></span>

### <a name="insert-controls-on-the-main-form"></a><span data-ttu-id="3da93-117">在主窗体上插入控件</span><span class="sxs-lookup"><span data-stu-id="3da93-117">Insert controls on the main form</span></span>

1.  <span data-ttu-id="3da93-118">向 Form1 中添加一个 ListBox 控件。</span><span class="sxs-lookup"><span data-stu-id="3da93-118">Add a ListBox control to Form1.</span></span> <span data-ttu-id="3da93-119">将其**Name**属性设置为**lstMain**。</span><span class="sxs-lookup"><span data-stu-id="3da93-119">Set its **Name** property to **lstMain**.</span></span>

2.  <span data-ttu-id="3da93-120">向 Form1 中添加另一个 ListBox 控件。</span><span class="sxs-lookup"><span data-stu-id="3da93-120">Add another ListBox control to Form1.</span></span> <span data-ttu-id="3da93-121">将其**Name**属性设置为**lstDetails**。</span><span class="sxs-lookup"><span data-stu-id="3da93-121">Set its **Name** property to **lstDetails**.</span></span>

3.  <span data-ttu-id="3da93-122">向 Form1 中添加一个 TextBox 控件。</span><span class="sxs-lookup"><span data-stu-id="3da93-122">Add a TextBox control to Form1.</span></span> <span data-ttu-id="3da93-123">将其**Name**属性设置为**txtDetails**。</span><span class="sxs-lookup"><span data-stu-id="3da93-123">Set its **Name** property to **txtDetails**.</span></span>

## <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="3da93-124">步骤 2: 初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="3da93-124">Step 2: Initialize the Main list box</span></span>

### <a name="declare-global-record-and-recordset-objects"></a><span data-ttu-id="3da93-125">声明全局 Record 和 Recordset 对象</span><span class="sxs-lookup"><span data-stu-id="3da93-125">Declare global Record and Recordset objects</span></span>

- <span data-ttu-id="3da93-126">将以下代码插入 Form1 的 (General) (Declarations) 中：</span><span class="sxs-lookup"><span data-stu-id="3da93-126">Insert the following code into the (General) (Declarations) for Form1:</span></span>
    
   ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
   ```
    
   <span data-ttu-id="3da93-127">上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="3da93-127">This code declares global object references for **Record** and **Recordset** objects that will be used later in this scenario.</span></span>

### <a name="connect-to-a-url-and-populate-lstmain"></a><span data-ttu-id="3da93-128">连接到 URL 并填充 lstMain</span><span class="sxs-lookup"><span data-stu-id="3da93-128">Connect to a URL and populate lstMain</span></span>

- <span data-ttu-id="3da93-129">将以下代码插入 Form1 的 Form Load 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="3da93-129">Insert the following code into the Form Load event handler for Form1:</span></span>
    
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
    
   <span data-ttu-id="3da93-130">上面的代码实例化全局 **Record** 和 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="3da93-130">This code instantiates the global **Record** and **Recordset** objects.</span></span> <span data-ttu-id="3da93-131">将使用指定为**ActiveConnection**的 URL 打开该**记录** `grec` 。</span><span class="sxs-lookup"><span data-stu-id="3da93-131">The **Record** `grec` is opened with a URL specified as the **ActiveConnection**.</span></span> <span data-ttu-id="3da93-132">如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。</span><span class="sxs-lookup"><span data-stu-id="3da93-132">If the URL exists, it is opened; if it does not already exist, it is created.</span></span> 
   
   <span data-ttu-id="3da93-133">请注意, 应将`https://servername/foldername/`您的环境中的有效 URL 替换为。</span><span class="sxs-lookup"><span data-stu-id="3da93-133">Note that you should replace `https://servername/foldername/` with a valid URL from your environment.</span></span> 
   
   <span data-ttu-id="3da93-134">将在**记录** `grec`的子级上打开**Recordset** `grs` 。</span><span class="sxs-lookup"><span data-stu-id="3da93-134">The **Recordset** `grs` is opened on the children of the **Record** `grec`.</span></span> <span data-ttu-id="3da93-135">然后, 将使用发布到 URL 的资源的文件名填充 lstMain。</span><span class="sxs-lookup"><span data-stu-id="3da93-135">The lstMain is then populated with the file names of the resources published to the URL.</span></span>

## <a name="step-3-populate-the-fields-list-box"></a><span data-ttu-id="3da93-136">步骤 3: 填充字段列表框</span><span class="sxs-lookup"><span data-stu-id="3da93-136">Step 3: Populate the Fields list box</span></span>

- <span data-ttu-id="3da93-137">将以下代码插入 lstMain 的 Click 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="3da93-137">Insert the following code into the Click event handler of lstMain:</span></span>

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

   <span data-ttu-id="3da93-138">此`rs`代码分别声明和实例化本地**Record**和`rec` **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="3da93-138">This code declares and instantiates local **Record** and **Recordset** objects `rec` and `rs`respectively.</span></span>

   <span data-ttu-id="3da93-139">将与 lstMain 中选定的资源相对应的行作为的当前行`grs`。</span><span class="sxs-lookup"><span data-stu-id="3da93-139">The row corresponding to the resource selected in lstMain is made the current row of `grs`.</span></span> <span data-ttu-id="3da93-140">然后, "**详细信息**" 列表框`rec`将被清除, 并使用当前`grs`行作为源打开。</span><span class="sxs-lookup"><span data-stu-id="3da93-140">The **Details** list box is then cleared and `rec` is opened with the current row of `grs` as the source.</span></span>

   <span data-ttu-id="3da93-141">如果资源是集合记录 (由**RecordType**指定), 则会在的子级上打开本地**Recordset** `rs` `rec`。</span><span class="sxs-lookup"><span data-stu-id="3da93-141">If the resource is a collection record (as specified by **RecordType**), the local **Recordset** `rs` is opened on the children of `rec`.</span></span> <span data-ttu-id="3da93-142">lstDetails 然后使用的行中的值进行填充`rs`。</span><span class="sxs-lookup"><span data-stu-id="3da93-142">lstDetails is then filled with the values from the rows of `rs`.</span></span>

   <span data-ttu-id="3da93-143">如果资源是简单记录, `recFields`则调用。</span><span class="sxs-lookup"><span data-stu-id="3da93-143">If the resource is a simple record, `recFields` is called.</span></span> <span data-ttu-id="3da93-144">有关`recFields`的详细信息, 请参阅下一步。</span><span class="sxs-lookup"><span data-stu-id="3da93-144">For more information about `recFields`, see the next step.</span></span>

   <span data-ttu-id="3da93-145">如果该资源是结构化文档，则将不实现任何代码。</span><span class="sxs-lookup"><span data-stu-id="3da93-145">No code is implemented if the resource is a structured document.</span></span>

## <a name="step-4-populate-the-details-text-box"></a><span data-ttu-id="3da93-146">步骤 4: 填充 "详细信息" 文本框</span><span class="sxs-lookup"><span data-stu-id="3da93-146">Step 4: Populate the Details text box</span></span>

- <span data-ttu-id="3da93-147">创建一个名为`recFields`的新子例程, 并插入以下代码:</span><span class="sxs-lookup"><span data-stu-id="3da93-147">Create a new subroutine named `recFields` and insert the following code:</span></span>

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

   <span data-ttu-id="3da93-148">此代码使用传递给`recFields`的简单记录的字段和值填充 lstDetails。</span><span class="sxs-lookup"><span data-stu-id="3da93-148">This code populates lstDetails with the fields and values of the simple record passed to `recFields`.</span></span> <span data-ttu-id="3da93-149">如果该资源是文本文件，则将从该资源记录打开文本的 **Stream**。</span><span class="sxs-lookup"><span data-stu-id="3da93-149">If the resource is a text file, a text **Stream** is opened from the resource record.</span></span> <span data-ttu-id="3da93-150">代码确定字符集是否为 ASCII, 并将**流**内容复制到中`txtDetails`。</span><span class="sxs-lookup"><span data-stu-id="3da93-150">The code determines if the character set is ASCII, and copies the **Stream** contents into `txtDetails`.</span></span>

