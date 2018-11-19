---
title: Internet 发布方案
TOCTitle: Internet publishing scenario
ms:assetid: 25a3fa8b-86ec-9e72-5e62-bf0d849479b7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249024(v=office.15)
ms:contentKeyID: 48543790
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1f481c4bc5cf11f9345458b3859c099b40a79885
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026447"
---
# <a name="internet-publishing-scenario"></a><span data-ttu-id="8aa5b-102">Internet 发布方案</span><span class="sxs-lookup"><span data-stu-id="8aa5b-102">Internet publishing scenario</span></span>

<span data-ttu-id="8aa5b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8aa5b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8aa5b-p101">此代码示例演示如何将 ADO 用于 Microsoft OLE DB Provider for Internet Publishing。在此方案中，您将创建一个 Visual Basic 应用程序，该应用程序使用 **Recordset** 、 **Record** 和 **Stream** 对象来显示用 Internet Publishing Provider 发布的资源的内容。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-p101">This code example demonstrates how to use ADO with the Microsoft OLE DB Provider for Internet Publishing. In this scenario, you will create a Visual Basic application that uses **Recordset**, **Record**, and **Stream** objects to display the contents of resources published with the Internet Publishing Provider.</span></span>

<span data-ttu-id="8aa5b-106">下列步骤是创建该方案所必需的步骤：</span><span class="sxs-lookup"><span data-stu-id="8aa5b-106">The following steps are necessary to create this scenario:</span></span> 

1. <span data-ttu-id="8aa5b-107">设置 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-107">Set up the Visual Basic project.</span></span>
2. <span data-ttu-id="8aa5b-108">初始化主列表框。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-108">Initialize the Main list box.</span></span>
3. <span data-ttu-id="8aa5b-109">填充 Fields 列表框。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-109">Populate the Fields list box.</span></span>
4. <span data-ttu-id="8aa5b-110">填充 Details 文本框。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-110">Populate the Details text box.</span></span>

## <a name="step-1-set-up-the-visual-basic-project"></a><span data-ttu-id="8aa5b-111">步骤 1： 设置 Visual Basic 项目</span><span class="sxs-lookup"><span data-stu-id="8aa5b-111">Step 1: Set up the Visual Basic project</span></span>

<span data-ttu-id="8aa5b-112">在该方案中，假设系统上装有 Microsoft Visual Basic 6.0 或更高版本、ADO 2.5 或更高版本以及 Microsoft OLE DB Provider for Internet Publishing。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-112">In this scenario, it is assumed that you have Microsoft Visual Basic 6.0 or later, ADO 2.5 or later, and the Microsoft OLE DB Provider for Internet Publishing installed on your system.</span></span>

### <a name="create-an-ado-project"></a><span data-ttu-id="8aa5b-113">创建 ADO 项目</span><span class="sxs-lookup"><span data-stu-id="8aa5b-113">Create an ADO project</span></span>

1.  <span data-ttu-id="8aa5b-114">在 Microsoft Visual Basic 中，新建一个标准 EXE 项目。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-114">In Microsoft Visual Basic, create a new Standard EXE project.</span></span>

2.  <span data-ttu-id="8aa5b-115">从**项目**菜单中，选择**引用**。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-115">From the **Project** menu, choose **References**.</span></span>

3.  <span data-ttu-id="8aa5b-116">选择**Microsoft ActiveX Data Objects 2.5 Library**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-116">Select **Microsoft ActiveX Data Objects 2.5 Library**, and then click **OK**.</span></span>

### <a name="insert-controls-on-the-main-form"></a><span data-ttu-id="8aa5b-117">在主窗体上插入控件</span><span class="sxs-lookup"><span data-stu-id="8aa5b-117">Insert controls on the main form</span></span>

1.  <span data-ttu-id="8aa5b-118">向 Form1 中添加一个 ListBox 控件。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-118">Add a ListBox control to Form1.</span></span> <span data-ttu-id="8aa5b-119">设置为**lstMain**其**Name**属性。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-119">Set its **Name** property to **lstMain**.</span></span>

2.  <span data-ttu-id="8aa5b-120">向 Form1 中添加另一个 ListBox 控件。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-120">Add another ListBox control to Form1.</span></span> <span data-ttu-id="8aa5b-121">设置为**lstDetails**其**Name**属性。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-121">Set its **Name** property to **lstDetails**.</span></span>

3.  <span data-ttu-id="8aa5b-122">向 Form1 中添加一个 TextBox 控件。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-122">Add a TextBox control to Form1.</span></span> <span data-ttu-id="8aa5b-123">设置为**txtDetails**其**Name**属性。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-123">Set its **Name** property to **txtDetails**.</span></span>

## <a name="step-2-initialize-the-main-list-box"></a><span data-ttu-id="8aa5b-124">步骤 2： 初始化主列表框</span><span class="sxs-lookup"><span data-stu-id="8aa5b-124">Step 2: Initialize the Main list box</span></span>

### <a name="declare-global-record-and-recordset-objects"></a><span data-ttu-id="8aa5b-125">声明全局 Record 和 Recordset 对象</span><span class="sxs-lookup"><span data-stu-id="8aa5b-125">Declare global Record and Recordset objects</span></span>

- <span data-ttu-id="8aa5b-126">将以下代码插入 Form1 的 (General) (Declarations) 中：</span><span class="sxs-lookup"><span data-stu-id="8aa5b-126">Insert the following code into the (General) (Declarations) for Form1:</span></span>
    
   ```vb 
     
    Option Explicit 
    Dim grec As Record 
    Dim grs As Recordset 
   ```
    
   <span data-ttu-id="8aa5b-127">上面的代码声明 **Record** 和 **Recordset** 对象的全局对象引用，在该方案的稍后部分将使用这些对象。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-127">This code declares global object references for **Record** and **Recordset** objects that will be used later in this scenario.</span></span>

### <a name="connect-to-a-url-and-populate-lstmain"></a><span data-ttu-id="8aa5b-128">连接到 URL 并填充 lstMain</span><span class="sxs-lookup"><span data-stu-id="8aa5b-128">Connect to a URL and populate lstMain</span></span>

- <span data-ttu-id="8aa5b-129">将以下代码插入 Form1 的 Form Load 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="8aa5b-129">Insert the following code into the Form Load event handler for Form1:</span></span>
    
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
    
   <span data-ttu-id="8aa5b-130">上面的代码实例化全局 **Record** 和 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-130">This code instantiates the global **Record** and **Recordset** objects.</span></span> <span data-ttu-id="8aa5b-131">**记录**`grec`打开与指定为**ActiveConnection**的 URL。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-131">The **Record** `grec` is opened with a URL specified as the **ActiveConnection**.</span></span> <span data-ttu-id="8aa5b-132">如果该 URL 存在，则将打开 grec；如果该 URL 尚不存在，则将创建 grec。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-132">If the URL exists, it is opened; if it does not already exist, it is created.</span></span> 
   
   <span data-ttu-id="8aa5b-133">请注意，您应替换`https://servername/foldername/`与环境中的有效 URL。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-133">Note that you should replace `https://servername/foldername/` with a valid URL from your environment.</span></span> 
   
   <span data-ttu-id="8aa5b-134">**Recordset** `grs` **记录**的子级上打开`grec`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-134">The **Recordset** `grs` is opened on the children of the **Record** `grec`.</span></span> <span data-ttu-id="8aa5b-135">LstMain 然后填入发布到该 URL 的资源的文件名。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-135">The lstMain is then populated with the file names of the resources published to the URL.</span></span>

## <a name="step-3-populate-the-fields-list-box"></a><span data-ttu-id="8aa5b-136">步骤 3： 填充字段列表框</span><span class="sxs-lookup"><span data-stu-id="8aa5b-136">Step 3: Populate the Fields list box</span></span>

- <span data-ttu-id="8aa5b-137">将以下代码插入 lstMain 的 Click 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="8aa5b-137">Insert the following code into the Click event handler of lstMain:</span></span>

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

   <span data-ttu-id="8aa5b-138">此代码声明并实例化本地**Record**和**Recordset**对象`rec`和`rs`分别。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-138">This code declares and instantiates local **Record** and **Recordset** objects `rec` and `rs`respectively.</span></span>

   <span data-ttu-id="8aa5b-139">LstMain 中所选资源相对应的行进行的当前行`grs`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-139">The row corresponding to the resource selected in lstMain is made the current row of `grs`.</span></span> <span data-ttu-id="8aa5b-140">然后清除**详细信息**列表框和`rec`打开与当前行的`grs`作为源。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-140">The **Details** list box is then cleared and `rec` is opened with the current row of `grs` as the source.</span></span>

   <span data-ttu-id="8aa5b-141">如果资源是集合记录 （由**RecordType**指定），则本地**Recordset** `rs`上的子级打开`rec`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-141">If the resource is a collection record (as specified by **RecordType**), the local **Recordset** `rs` is opened on the children of `rec`.</span></span> <span data-ttu-id="8aa5b-142">然后 lstdetails 将用的行的值`rs`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-142">lstDetails is then filled with the values from the rows of `rs`.</span></span>

   <span data-ttu-id="8aa5b-143">如果资源是一个简单的记录，`recFields`调用。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-143">If the resource is a simple record, `recFields` is called.</span></span> <span data-ttu-id="8aa5b-144">有关详细信息`recFields`，请参阅下一步。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-144">For more information about `recFields`, see the next step.</span></span>

   <span data-ttu-id="8aa5b-145">如果该资源是结构化文档，则将不实现任何代码。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-145">No code is implemented if the resource is a structured document.</span></span>

## <a name="step-4-populate-the-details-text-box"></a><span data-ttu-id="8aa5b-146">步骤 4： 填充细节文本框</span><span class="sxs-lookup"><span data-stu-id="8aa5b-146">Step 4: Populate the Details text box</span></span>

- <span data-ttu-id="8aa5b-147">创建一个名为的新子例程`recFields`，插入以下代码：</span><span class="sxs-lookup"><span data-stu-id="8aa5b-147">Create a new subroutine named `recFields` and insert the following code:</span></span>

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

   <span data-ttu-id="8aa5b-148">此代码填充 lstDetails 具有字段和简单的记录的值传递到`recFields`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-148">This code populates lstDetails with the fields and values of the simple record passed to `recFields`.</span></span> <span data-ttu-id="8aa5b-149">如果该资源是文本文件，则将从该资源记录打开文本的 **Stream** 。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-149">If the resource is a text file, a text **Stream** is opened from the resource record.</span></span> <span data-ttu-id="8aa5b-150">该代码将确定字符集是否 ASCII，并将复制到的**流**内容`txtDetails`。</span><span class="sxs-lookup"><span data-stu-id="8aa5b-150">The code determines if the character set is ASCII, and copies the **Stream** contents into `txtDetails`.</span></span>

