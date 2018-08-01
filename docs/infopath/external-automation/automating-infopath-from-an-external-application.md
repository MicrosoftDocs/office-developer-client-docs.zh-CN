---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 提供应用程序中使用的应用程序对象和 XDocuments 集合的方法使用 COM 和脚本编写的代码的自动化。
ms.openlocfilehash: 0e3fcc50ec11f5fc8791d37144767bf0398ccda7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773872"
---
# <a name="automating-infopath-from-an-external-application"></a><span data-ttu-id="e1726-103">从外部应用程序自动执行 InfoPath</span><span class="sxs-lookup"><span data-stu-id="e1726-103">Automating InfoPath from an external application</span></span>

<span data-ttu-id="e1726-104">Microsoft InfoPath 提供应用程序中使用的**应用程序**对象和**XDocuments**集合的方法使用 COM 和脚本编写的代码的自动化。</span><span class="sxs-lookup"><span data-stu-id="e1726-104">Microsoft InfoPath provides application automation from code written using COM and script by using methods of the **Application** object and the **XDocuments** collection.</span></span> 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a><span data-ttu-id="e1726-105">应用程序和 XDocument 对象概述</span><span class="sxs-lookup"><span data-stu-id="e1726-105">Overview of the Application and XDocument Objects</span></span>

<span data-ttu-id="e1726-106">**Application**对象包含用于自动化的以下方法：</span><span class="sxs-lookup"><span data-stu-id="e1726-106">The **Application** object contains the following methods used for automation:</span></span> 
  
|<span data-ttu-id="e1726-107">**方法**</span><span class="sxs-lookup"><span data-stu-id="e1726-107">**Method**</span></span>|<span data-ttu-id="e1726-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1726-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1726-109">**CacheSolution**</span><span class="sxs-lookup"><span data-stu-id="e1726-109">**CacheSolution**</span></span> <br/> |<span data-ttu-id="e1726-110">检查缓存中，如果需要，从表单模板的发布位置更新它。</span><span class="sxs-lookup"><span data-stu-id="e1726-110">Examines the in the cache and, if necessary, updates it from the published location of the form template.</span></span>  <br/> |
|<span data-ttu-id="e1726-111">**Quit**</span><span class="sxs-lookup"><span data-stu-id="e1726-111">**Quit**</span></span> <br/> |<span data-ttu-id="e1726-112">退出 Microsoft Office InfoPath 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1726-112">Quits the Microsoft Office InfoPath application.</span></span>  <br/> |
|<span data-ttu-id="e1726-113">**RegisterSolution**</span><span class="sxs-lookup"><span data-stu-id="e1726-113">**RegisterSolution**</span></span> <br/> |<span data-ttu-id="e1726-114">安装指定的 Microsoft Office InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="e1726-114">Installs the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
|<span data-ttu-id="e1726-115">**UnregisterSolution**</span><span class="sxs-lookup"><span data-stu-id="e1726-115">**UnregisterSolution**</span></span> <br/> |<span data-ttu-id="e1726-116">卸载指定的 Microsoft Office InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="e1726-116">Uninstalls the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
   
<span data-ttu-id="e1726-117">**XDocuments**集合包含可用于外部自动化的以下方法：</span><span class="sxs-lookup"><span data-stu-id="e1726-117">The **XDocuments** collection contains the following methods that can be used for external automation:</span></span> 
  
|<span data-ttu-id="e1726-118">**方法**</span><span class="sxs-lookup"><span data-stu-id="e1726-118">**Method**</span></span>|<span data-ttu-id="e1726-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1726-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1726-120">**Close** 方法</span><span class="sxs-lookup"><span data-stu-id="e1726-120">**Close** method</span></span>  <br/> |<span data-ttu-id="e1726-121">关闭指定的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="e1726-121">Closes the specified Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="e1726-122">**New** 方法</span><span class="sxs-lookup"><span data-stu-id="e1726-122">**New** method</span></span>  <br/> |<span data-ttu-id="e1726-123">创建新的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="e1726-123">Creates a new Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="e1726-124">**NewFromSolution** 方法</span><span class="sxs-lookup"><span data-stu-id="e1726-124">**NewFromSolution** method</span></span>  <br/> |<span data-ttu-id="e1726-125">创建基于指定的表单模板的新的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="e1726-125">Creates a new Microsoft Office InfoPath form based on the specified form template.</span></span>  <br/> |
|<span data-ttu-id="e1726-126">**NewFromSolutionWithData** 方法</span><span class="sxs-lookup"><span data-stu-id="e1726-126">**NewFromSolutionWithData** method</span></span>  <br/> |<span data-ttu-id="e1726-127">创建新的 Microsoft Office InfoPath 表单使用指定的 XML 数据和表单模板。</span><span class="sxs-lookup"><span data-stu-id="e1726-127">Creates a new Microsoft Office InfoPath form using the specified XML data and form template.</span></span>  <br/> |
|<span data-ttu-id="e1726-128">**Open** 方法</span><span class="sxs-lookup"><span data-stu-id="e1726-128">**Open** method</span></span>  <br/> |<span data-ttu-id="e1726-129">打开指定的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="e1726-129">Opens the specified Microsoft Office InfoPath form.</span></span>  <br/> |
   
<span data-ttu-id="e1726-130">若要使用的外部应用程序的**应用程序**对象，您使用**CreateObject**函数的 ProgID 的 InfoPath 应用程序 ("InfoPath.Application") 创建一个对象变量，代表 InfoPath 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1726-130">To use the **Application** object from an external application, you use the **CreateObject** function with the ProgID of the InfoPath application ("InfoPath.Application") to create an object variable that represents the InfoPath application.</span></span> <span data-ttu-id="e1726-131">然后，您可以使用**XDocuments**属性来访问**XDocuments**集合，并使用其方法打开或创建 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="e1726-131">You can then use the **XDocuments** property to access the **XDocuments** collection and use its methods to open or create an InfoPath form.</span></span> <span data-ttu-id="e1726-132">下面的示例演示了如何创建使用 Microsoft Visual Basic 6.0 或 Visual Basic for Applications (VBA) 编程语言的**应用程序**对象的引用：</span><span class="sxs-lookup"><span data-stu-id="e1726-132">The following example demonstrates the creation of a reference to the **Application** object using the Microsoft Visual Basic 6.0 or Visual Basic for Applications (VBA) programming language:</span></span> 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> <span data-ttu-id="e1726-133">由于**CreateObject**函数创建对象变量使用后期绑定，自动语句完成将不可用 Visual Basic 编辑器中。</span><span class="sxs-lookup"><span data-stu-id="e1726-133">Because the **CreateObject** function creates an object variable using late binding, automatic statement completion will not be available in the Visual Basic Editor.</span></span> <span data-ttu-id="e1726-134">请参阅有关正确的调用语法前面的表中的链接。</span><span class="sxs-lookup"><span data-stu-id="e1726-134">Refer to the links in the preceding tables for information about the correct calling syntax.</span></span> 
  

