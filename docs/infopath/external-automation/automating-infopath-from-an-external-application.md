---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 通过使用 Application 对象和 XDocuments 集合的方法通过 COM 和脚本编写的代码提供应用程序自动化。
ms.openlocfilehash: 7eccbca34b93aff7909de92eebc04d012d4dd97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412665"
---
# <a name="automating-infopath-from-an-external-application"></a><span data-ttu-id="ac8db-103">从外部应用程序自动执行 InfoPath</span><span class="sxs-lookup"><span data-stu-id="ac8db-103">Automating InfoPath from an external application</span></span>

<span data-ttu-id="ac8db-104">Microsoft InfoPath 通过使用 **Application** 对象和 **XDocuments** 集合的方法通过 COM 和脚本编写的代码提供应用程序自动化。</span><span class="sxs-lookup"><span data-stu-id="ac8db-104">Microsoft InfoPath provides application automation from code written using COM and script by using methods of the **Application** object and the **XDocuments** collection.</span></span> 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a><span data-ttu-id="ac8db-105">Application 和 XDocument 对象概述</span><span class="sxs-lookup"><span data-stu-id="ac8db-105">Overview of the Application and XDocument Objects</span></span>

<span data-ttu-id="ac8db-106">**Application** 对象包含以下用于自动化的方法：</span><span class="sxs-lookup"><span data-stu-id="ac8db-106">The **Application** object contains the following methods used for automation:</span></span> 
  
|<span data-ttu-id="ac8db-107">**方法**</span><span class="sxs-lookup"><span data-stu-id="ac8db-107">**Method**</span></span>|<span data-ttu-id="ac8db-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac8db-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac8db-109">**CacheSolution**</span><span class="sxs-lookup"><span data-stu-id="ac8db-109">**CacheSolution**</span></span> <br/> |<span data-ttu-id="ac8db-110">检查缓存中的 ，并在必要时从缓存的发布位置更新表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac8db-110">Examines the in the cache and, if necessary, updates it from the published location of the form template.</span></span>  <br/> |
|<span data-ttu-id="ac8db-111">**Quit**</span><span class="sxs-lookup"><span data-stu-id="ac8db-111">**Quit**</span></span> <br/> |<span data-ttu-id="ac8db-112">退出Microsoft Office InfoPath 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac8db-112">Quits the Microsoft Office InfoPath application.</span></span>  <br/> |
|<span data-ttu-id="ac8db-113">**RegisterSolution**</span><span class="sxs-lookup"><span data-stu-id="ac8db-113">**RegisterSolution**</span></span> <br/> |<span data-ttu-id="ac8db-114">安装 InfoPath Microsoft Office指定的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac8db-114">Installs the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
|<span data-ttu-id="ac8db-115">**UnregisterSolution**</span><span class="sxs-lookup"><span data-stu-id="ac8db-115">**UnregisterSolution**</span></span> <br/> |<span data-ttu-id="ac8db-116">卸载 InfoPath Microsoft Office指定的表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac8db-116">Uninstalls the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
   
<span data-ttu-id="ac8db-117">**XDocuments** 集合包含以下可用于外部自动化的方法：</span><span class="sxs-lookup"><span data-stu-id="ac8db-117">The **XDocuments** collection contains the following methods that can be used for external automation:</span></span> 
  
|<span data-ttu-id="ac8db-118">**方法**</span><span class="sxs-lookup"><span data-stu-id="ac8db-118">**Method**</span></span>|<span data-ttu-id="ac8db-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac8db-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac8db-120">**Close** 方法</span><span class="sxs-lookup"><span data-stu-id="ac8db-120">**Close** method</span></span>  <br/> |<span data-ttu-id="ac8db-121">关闭 InfoPath Microsoft Office指定的表单。</span><span class="sxs-lookup"><span data-stu-id="ac8db-121">Closes the specified Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="ac8db-122">**New** 方法</span><span class="sxs-lookup"><span data-stu-id="ac8db-122">**New** method</span></span>  <br/> |<span data-ttu-id="ac8db-123">新建 InfoPath Microsoft Office表单。</span><span class="sxs-lookup"><span data-stu-id="ac8db-123">Creates a new Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="ac8db-124">**NewFromSolution** 方法</span><span class="sxs-lookup"><span data-stu-id="ac8db-124">**NewFromSolution** method</span></span>  <br/> |<span data-ttu-id="ac8db-125">基于指定的表单Microsoft Office InfoPath 表单创建一表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac8db-125">Creates a new Microsoft Office InfoPath form based on the specified form template.</span></span>  <br/> |
|<span data-ttu-id="ac8db-126">**NewFromSolutionWithData** 方法</span><span class="sxs-lookup"><span data-stu-id="ac8db-126">**NewFromSolutionWithData** method</span></span>  <br/> |<span data-ttu-id="ac8db-127">使用指定的 XML Microsoft Office创建一个新的 InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="ac8db-127">Creates a new Microsoft Office InfoPath form using the specified XML data and form template.</span></span>  <br/> |
|<span data-ttu-id="ac8db-128">**Open** 方法</span><span class="sxs-lookup"><span data-stu-id="ac8db-128">**Open** method</span></span>  <br/> |<span data-ttu-id="ac8db-129">打开 InfoPath Microsoft Office指定的表单。</span><span class="sxs-lookup"><span data-stu-id="ac8db-129">Opens the specified Microsoft Office InfoPath form.</span></span>  <br/> |
   
<span data-ttu-id="ac8db-130">若要使用外部应用程序中的 **Application** 对象，请使用 **CreateObject** 函数和 InfoPath 应用程序 ("InfoPath.Application") 的 ProgID 来创建一个代表 InfoPath 应用程序的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ac8db-130">To use the **Application** object from an external application, you use the **CreateObject** function with the ProgID of the InfoPath application ("InfoPath.Application") to create an object variable that represents the InfoPath application.</span></span> <span data-ttu-id="ac8db-131">然后，可以使用 **XDocuments** 属性访问 **XDocuments** 集合并使用其方法打开或创建 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="ac8db-131">You can then use the **XDocuments** property to access the **XDocuments** collection and use its methods to open or create an InfoPath form.</span></span> <span data-ttu-id="ac8db-132">以下示例演示了使用 Microsoft Visual Basic 6.0 或 Visual Basic for Applications (VBA 创建对 **Application**) 的引用：</span><span class="sxs-lookup"><span data-stu-id="ac8db-132">The following example demonstrates the creation of a reference to the **Application** object using the Microsoft Visual Basic 6.0 or Visual Basic for Applications (VBA) programming language:</span></span> 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> <span data-ttu-id="ac8db-133">由于 **CreateObject** 函数使用晚期绑定创建对象变量，因此自动语句完成功能在编辑器中Visual Basic可用。</span><span class="sxs-lookup"><span data-stu-id="ac8db-133">Because the **CreateObject** function creates an object variable using late binding, automatic statement completion will not be available in the Visual Basic Editor.</span></span> <span data-ttu-id="ac8db-134">有关正确的调用语法的信息，请参阅前面表格中的链接。</span><span class="sxs-lookup"><span data-stu-id="ac8db-134">Refer to the links in the preceding tables for information about the correct calling syntax.</span></span> 
  

