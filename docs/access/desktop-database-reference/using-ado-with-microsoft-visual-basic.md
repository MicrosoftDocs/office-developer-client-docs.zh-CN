---
title: 在 Microsoft Visual Basic 中使用 ADO
TOCTitle: Using ADO with Microsoft Visual Basic
ms:assetid: 5e0fb2ec-42aa-e181-386f-099607ac7400
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249338(v=office.15)
ms:contentKeyID: 48545130
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aa1f9a3c7601601a1ce48ea3912a4f759d436e4f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468879"
---
# <a name="using-ado-with-microsoft-visual-basic"></a><span data-ttu-id="835a4-102">在 Microsoft Visual Basic 中使用 ADO</span><span class="sxs-lookup"><span data-stu-id="835a4-102">Using ADO with Microsoft Visual Basic</span></span>


<span data-ttu-id="835a4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="835a4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="835a4-p101">无论是使用 Visual Basic 还是使用 Visual Basic for Applications，在设置 ADO 项目和编写 ADO 代码时都类似。本主题介绍了如何在 Visual Basic 和 Visual Basic for Applications 中使用 ADO，并注明了二者之间的区别。</span><span class="sxs-lookup"><span data-stu-id="835a4-p101">Setting up an ADO project and writing ADO code is similar whether you use Visual Basic or Visual Basic for Applications. This topic addresses using ADO with both Visual Basic and Visual Basic for Applications and notes any differences.</span></span>

## <a name="referencing-the-ado-library"></a><span data-ttu-id="835a4-106">引用 ADO 库</span><span class="sxs-lookup"><span data-stu-id="835a4-106">Referencing the ADO Library</span></span>

<span data-ttu-id="835a4-107">ADO 库必须由项目引用。</span><span class="sxs-lookup"><span data-stu-id="835a4-107">The ADO library must be referenced by your project.</span></span>

<span data-ttu-id="835a4-108">**从 Microsoft Visual Basic 中引用 ADO**</span><span class="sxs-lookup"><span data-stu-id="835a4-108">**To reference ADO from Microsoft Visual Basic**</span></span>

1.  <span data-ttu-id="835a4-109">在 Visual Basic 中，从**项目**菜单中，选择**引用...**。</span><span class="sxs-lookup"><span data-stu-id="835a4-109">In Visual Basic, from the **Project** menu, select **References...**.</span></span>

2.  <span data-ttu-id="835a4-110">从列表中选择**Microsoft ActiveX 数据对象 x.x 库**。</span><span class="sxs-lookup"><span data-stu-id="835a4-110">Select **Microsoft ActiveX Data Objects x.x Library** from the list.</span></span> <span data-ttu-id="835a4-111">至少验证以下库也将被选中：</span><span class="sxs-lookup"><span data-stu-id="835a4-111">Verify that at least the following libraries are also selected:</span></span>
    
    - <span data-ttu-id="835a4-112">Visual Basic for Applications</span><span class="sxs-lookup"><span data-stu-id="835a4-112">Visual Basic for Applications</span></span>
    
    - <span data-ttu-id="835a4-113">Visual Basic 运行时对象和过程</span><span class="sxs-lookup"><span data-stu-id="835a4-113">Visual Basic runtime objects and procedures</span></span>
    
    - <span data-ttu-id="835a4-114">Visual Basic 对象和过程</span><span class="sxs-lookup"><span data-stu-id="835a4-114">Visual Basic objects and procedures</span></span>
    
    - <span data-ttu-id="835a4-115">OLE 自动化</span><span class="sxs-lookup"><span data-stu-id="835a4-115">OLE Automation</span></span>

3.  <span data-ttu-id="835a4-116">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="835a4-116">Click **OK**.</span></span>

<span data-ttu-id="835a4-117">在 Visual Basic for Applications（如使用 Microsoft Access 时）中可以同样轻松地使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="835a4-117">You can use ADO just as easily with Visual Basic for Applications, using Microsoft Access, for example.</span></span>

<span data-ttu-id="835a4-118">**从 Microsoft Access 中引用 ADO**</span><span class="sxs-lookup"><span data-stu-id="835a4-118">**To reference ADO from Microsoft Access**</span></span>

1.  <span data-ttu-id="835a4-119">在 Microsoft Access 中，选择或创建一个模块，从**数据库**窗口中的**模块**选项卡。</span><span class="sxs-lookup"><span data-stu-id="835a4-119">In Microsoft Access, select or create a module from the **Modules** tab in the **Database** window.</span></span>

2.  <span data-ttu-id="835a4-120">从**工具**菜单中，选择**引用...**。</span><span class="sxs-lookup"><span data-stu-id="835a4-120">From the **Tools** menu, select **References...**.</span></span>

3.  <span data-ttu-id="835a4-121">从列表中选择**Microsoft ActiveX 数据对象 x.x 库**。</span><span class="sxs-lookup"><span data-stu-id="835a4-121">Select **Microsoft ActiveX Data Objects x.x Library** from the list.</span></span> <span data-ttu-id="835a4-122">至少验证以下库也将被选中：</span><span class="sxs-lookup"><span data-stu-id="835a4-122">Verify that at least the following libraries are also selected:</span></span>
    
    - <span data-ttu-id="835a4-123">Visual Basic for Applications</span><span class="sxs-lookup"><span data-stu-id="835a4-123">Visual Basic for Applications</span></span>
    
    - <span data-ttu-id="835a4-124">Microsoft Access 11.0 对象库（或更高版本）</span><span class="sxs-lookup"><span data-stu-id="835a4-124">Microsoft Access 11.0 Object Library (or later)</span></span>

4.  <span data-ttu-id="835a4-125">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="835a4-125">Click **OK**.</span></span>

## <a name="creating-ado-objects-in-visual-basic"></a><span data-ttu-id="835a4-126">在 Visual Basic 中创建 ADO</span><span class="sxs-lookup"><span data-stu-id="835a4-126">Creating ADO Objects in Visual Basic</span></span>

<span data-ttu-id="835a4-127">若要创建自动化变量以及该变量的对象实例，可以使用以下两个方法： **Dim** 或 **CreateObject** 。</span><span class="sxs-lookup"><span data-stu-id="835a4-127">To create an automation variable and an instance of an object for that variable, you can use two methods: **Dim** or **CreateObject**.</span></span>

## <a name="dim"></a><span data-ttu-id="835a4-128">Dim</span><span class="sxs-lookup"><span data-stu-id="835a4-128">Dim</span></span>

<span data-ttu-id="835a4-129">可以使用 **New** 关键字和 **Dim** ，在一个步骤中同时声明和实例化 ADO 对象：</span><span class="sxs-lookup"><span data-stu-id="835a4-129">You can use the **New** keyword with **Dim** to declare and instantiate ADO objects in one step:</span></span>

```vb 
 
Dim conn As New ADODB.Connection 
```

<span data-ttu-id="835a4-130">或者，也可以将 **Dim** 语句声明和对象实例化分为两个步骤：</span><span class="sxs-lookup"><span data-stu-id="835a4-130">Alternately, the **Dim** statement declaration and object instantiation can also be two steps:</span></span>

```vb 
 
Dim conn As ADODB.Connection 
Set conn = New ADODB.Connection 
```


> [!NOTE]
> <P><span data-ttu-id="835a4-131">不需要明确用<STRONG>Dim</STRONG>语句，假定您正确引用 ADO 库项目中使用 progid ADODB。</span><span class="sxs-lookup"><span data-stu-id="835a4-131">It is not required to explicitly use the ADODB progid with the <STRONG>Dim</STRONG> statement, assuming you have properly referenced the ADO library in your project.</span></span> <span data-ttu-id="835a4-132">不过，使用它可以确保不会与其他库产生命名冲突。</span><span class="sxs-lookup"><span data-stu-id="835a4-132">However, using it ensures that you won't have naming conflicts with other libraries.</span></span></P>



<span data-ttu-id="835a4-133">例如，如果同一个项目中同时包括针对 ADO 和 DAO 的引用，那么，您可以使用限定符来指定在实例化 **Recordset** 对象时所使用的对象模型，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="835a4-133">For example, if you include references to both ADO and DAO in the same project, you should include a qualifier to specify which object model to use when instantiating **Recordset** objects, as in the following code:</span></span>  
<span data-ttu-id="835a4-134">Dim adoRS 作为 ADODB。记录集</span><span class="sxs-lookup"><span data-stu-id="835a4-134">Dim adoRS As ADODB.Recordset</span></span>  
  
<span data-ttu-id="835a4-135">Dim daoRS 作为 DAO。记录集</span><span class="sxs-lookup"><span data-stu-id="835a4-135">Dim daoRS As DAO.Recordset</span></span>

## <a name="createobject"></a><span data-ttu-id="835a4-136">CreateObject</span><span class="sxs-lookup"><span data-stu-id="835a4-136">CreateObject</span></span>

<span data-ttu-id="835a4-137">采用 **CreateObject** 方法时，声明和对象实例化必须是两个独立的步骤：</span><span class="sxs-lookup"><span data-stu-id="835a4-137">With the **CreateObject** method, the declaration and object instantiation must be two discrete steps:</span></span>

```vb 
 
Dim conn1 
Set conn1 = CreateObject("ADODB.Connection") As Object 
```

<span data-ttu-id="835a4-p105">用 **CreateObject** 实例化的对象是后期绑定的，这表明这些对象不是强类型的，且命令行完成被禁用。不过，允许您在项目中跳过对 ADO 库的引用，并实例化对象的特定版本。例如：</span><span class="sxs-lookup"><span data-stu-id="835a4-p105">Objects instantiated with **CreateObject** are late-bound, which means that they are not strongly typed and command-line completion is disabled. However, it does allow you to skip referencing the ADO library from your project, and enables you to instantiate specific versions of objects. For example:</span></span>

```vb 
 
Set conn1 = CreateObject("ADODB.Connection.2.0") As Object 
```

<span data-ttu-id="835a4-141">您也可以通过专门创建一个针对 ADO 版本 2.0 类型库的引用并创建对象来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="835a4-141">You could also accomplish this by specifically creating a reference to the ADO version 2.0 type library and creating the object.</span></span>

<span data-ttu-id="835a4-142">用 **CreateObject** 方法实例化对象通常要比用 **Dim** 语句慢。</span><span class="sxs-lookup"><span data-stu-id="835a4-142">Instantiating objects with the **CreateObject** method is typically slower than using the **Dim** statement.</span></span>

## <a name="handling-events"></a><span data-ttu-id="835a4-143">处理事件</span><span class="sxs-lookup"><span data-stu-id="835a4-143">Handling Events</span></span>

<span data-ttu-id="835a4-p106">若要在 Microsoft Visual Basic 中处理 ADO 事件，必须使用 **WithEvents** 关键字声明一个模块级变量。该变量可以只声明为类模块的一部分，但必须在模块级进行声明。有关处理 ADO 事件的更完整的讨论，请参阅 [第 7 章：处理 ADO 事件](chapter-7-handling-ado-events.md)。</span><span class="sxs-lookup"><span data-stu-id="835a4-p106">In order to handle ADO events in Microsoft Visual Basic, you must declare a module-level variable using the **WithEvents** keyword. The variable can be declared only as part of a class module and must be declared at the module level. For a more complete discussion of handling ADO events, see [Chapter 7: Handling ADO Events](chapter-7-handling-ado-events.md).</span></span>

## <a name="visual-basic-examples"></a><span data-ttu-id="835a4-147">Visual Basic 示例</span><span class="sxs-lookup"><span data-stu-id="835a4-147">Visual Basic Examples</span></span>

<span data-ttu-id="835a4-p107">ADO 文档中附带了许多 Visual Basic 示例。有关详细信息，请参阅 [Microsoft Visual Basic 中的 ADO 代码示例](ado-code-examples-in-microsoft-visual-basic.md).</span><span class="sxs-lookup"><span data-stu-id="835a4-p107">Many Visual Basic examples are included with the ADO documentation. For more information, see [ADO Code Examples in Microsoft Visual Basic](ado-code-examples-in-microsoft-visual-basic.md).</span></span>

