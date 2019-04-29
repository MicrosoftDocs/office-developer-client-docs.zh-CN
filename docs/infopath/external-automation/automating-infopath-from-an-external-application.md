---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 通过使用 application 对象和 XDocuments 集合的方法, 从使用 COM 和脚本编写的代码中提供应用程序自动化。
ms.openlocfilehash: 7eccbca34b93aff7909de92eebc04d012d4dd97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412665"
---
# <a name="automating-infopath-from-an-external-application"></a><span data-ttu-id="9dcfc-103">从外部应用程序自动执行 InfoPath</span><span class="sxs-lookup"><span data-stu-id="9dcfc-103">Automating InfoPath from an external application</span></span>

<span data-ttu-id="9dcfc-104">Microsoft InfoPath 通过使用**application**对象和**XDocuments**集合的方法, 从使用 COM 和脚本编写的代码中提供应用程序自动化。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-104">Microsoft InfoPath provides application automation from code written using COM and script by using methods of the **Application** object and the **XDocuments** collection.</span></span> 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a><span data-ttu-id="9dcfc-105">Application 和 XDocument 对象概述</span><span class="sxs-lookup"><span data-stu-id="9dcfc-105">Overview of the Application and XDocument Objects</span></span>

<span data-ttu-id="9dcfc-106">**Application**对象包含用于自动化的以下方法:</span><span class="sxs-lookup"><span data-stu-id="9dcfc-106">The **Application** object contains the following methods used for automation:</span></span> 
  
|<span data-ttu-id="9dcfc-107">**方法**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-107">**Method**</span></span>|<span data-ttu-id="9dcfc-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9dcfc-109">**CacheSolution**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-109">**CacheSolution**</span></span> <br/> |<span data-ttu-id="9dcfc-110">检查缓存中的, 如有必要, 从表单模板的发布位置更新它。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-110">Examines the in the cache and, if necessary, updates it from the published location of the form template.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-111">**Quit**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-111">**Quit**</span></span> <br/> |<span data-ttu-id="9dcfc-112">退出 Microsoft Office InfoPath 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-112">Quits the Microsoft Office InfoPath application.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-113">**RegisterSolution**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-113">**RegisterSolution**</span></span> <br/> |<span data-ttu-id="9dcfc-114">安装指定的 Microsoft Office InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-114">Installs the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-115">**UnregisterSolution**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-115">**UnregisterSolution**</span></span> <br/> |<span data-ttu-id="9dcfc-116">卸载指定的 Microsoft Office InfoPath 表单模板。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-116">Uninstalls the specified Microsoft Office InfoPath form template.</span></span>  <br/> |
   
<span data-ttu-id="9dcfc-117">**XDocuments**集合包含可用于外部自动化的以下方法:</span><span class="sxs-lookup"><span data-stu-id="9dcfc-117">The **XDocuments** collection contains the following methods that can be used for external automation:</span></span> 
  
|<span data-ttu-id="9dcfc-118">**方法**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-118">**Method**</span></span>|<span data-ttu-id="9dcfc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9dcfc-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9dcfc-120">**Close** 方法</span><span class="sxs-lookup"><span data-stu-id="9dcfc-120">**Close** method</span></span>  <br/> |<span data-ttu-id="9dcfc-121">关闭指定的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-121">Closes the specified Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-122">**New** 方法</span><span class="sxs-lookup"><span data-stu-id="9dcfc-122">**New** method</span></span>  <br/> |<span data-ttu-id="9dcfc-123">创建一个新的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-123">Creates a new Microsoft Office InfoPath form.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-124">**NewFromSolution** 方法</span><span class="sxs-lookup"><span data-stu-id="9dcfc-124">**NewFromSolution** method</span></span>  <br/> |<span data-ttu-id="9dcfc-125">基于指定的表单模板创建新的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-125">Creates a new Microsoft Office InfoPath form based on the specified form template.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-126">**NewFromSolutionWithData** 方法</span><span class="sxs-lookup"><span data-stu-id="9dcfc-126">**NewFromSolutionWithData** method</span></span>  <br/> |<span data-ttu-id="9dcfc-127">使用指定的 XML 数据和表单模板创建新的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-127">Creates a new Microsoft Office InfoPath form using the specified XML data and form template.</span></span>  <br/> |
|<span data-ttu-id="9dcfc-128">**Open** 方法</span><span class="sxs-lookup"><span data-stu-id="9dcfc-128">**Open** method</span></span>  <br/> |<span data-ttu-id="9dcfc-129">打开指定的 Microsoft Office InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-129">Opens the specified Microsoft Office InfoPath form.</span></span>  <br/> |
   
<span data-ttu-id="9dcfc-130">若要从外部应用程序使用**application**对象, 请将**CreateObject**函数与 InfoPath 应用程序的 ProgID ("InfoPath. 应用程序") 结合使用, 以创建代表 InfoPath 应用程序的对象变量。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-130">To use the **Application** object from an external application, you use the **CreateObject** function with the ProgID of the InfoPath application ("InfoPath.Application") to create an object variable that represents the InfoPath application.</span></span> <span data-ttu-id="9dcfc-131">然后, 可以使用**XDocuments**属性访问**XDocuments**集合并使用其方法打开或创建 InfoPath 表单。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-131">You can then use the **XDocuments** property to access the **XDocuments** collection and use its methods to open or create an InfoPath form.</span></span> <span data-ttu-id="9dcfc-132">下面的示例演示如何使用 Microsoft Visual basic 6.0 或 Visual basic for Applications (VBA) 编程语言创建对**Application**对象的引用:</span><span class="sxs-lookup"><span data-stu-id="9dcfc-132">The following example demonstrates the creation of a reference to the **Application** object using the Microsoft Visual Basic 6.0 or Visual Basic for Applications (VBA) programming language:</span></span> 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> <span data-ttu-id="9dcfc-133">由于**CreateObject**函数使用后期绑定创建对象变量, 因此在 Visual Basic 编辑器中, 自动语句完成将不可用。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-133">Because the **CreateObject** function creates an object variable using late binding, automatic statement completion will not be available in the Visual Basic Editor.</span></span> <span data-ttu-id="9dcfc-134">有关正确的调用语法的信息, 请参阅上表中的链接。</span><span class="sxs-lookup"><span data-stu-id="9dcfc-134">Refer to the links in the preceding tables for information about the correct calling syntax.</span></span> 
  

