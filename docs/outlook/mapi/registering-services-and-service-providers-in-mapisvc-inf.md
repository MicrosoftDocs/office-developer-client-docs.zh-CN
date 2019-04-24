---
title: 在 mapisvc.inf 中注册服务和服务提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a04acf17-4b2d-458e-9852-b6074acac096
description: '上次修改时间: 2013 年7月18日'
ms.openlocfilehash: adc6318ab36818b4c423bb6b1dc1b083b3fb54eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328369"
---
# <a name="registering-services-and-service-providers-in-mapisvcinf"></a><span data-ttu-id="af3b4-103">在 mapisvc.inf 中注册服务和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="af3b4-103">Registering Services and Service Providers in MapiSvc.inf</span></span>

 
  
<span data-ttu-id="af3b4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af3b4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af3b4-105">若要在系统上安装新的提供程序, 则需要更新 mapisvc.inf 文件以指向新的提供程序。</span><span class="sxs-lookup"><span data-stu-id="af3b4-105">Installing a new provider on a system requires updating the MapiSvc.inf file to point to the new provider.</span></span> <span data-ttu-id="af3b4-106">配置过程中设置的标准属性, 其中包括以下内容: 通知 MAPI 查找提供程序的动态链接库 (.dll) 的位置:</span><span class="sxs-lookup"><span data-stu-id="af3b4-106">Standard properties set during configuration, which include the following, inform MAPI where to find the provider's dynamic-link library (.dll):</span></span>
  
- <span data-ttu-id="af3b4-107">**PR_SERVICE_DLL_NAME**在 **[邮件服务]** 部分中指定。</span><span class="sxs-lookup"><span data-stu-id="af3b4-107">The **PR_SERVICE_DLL_NAME** is specified in the **[Message Service]** section.</span></span> 
    
- <span data-ttu-id="af3b4-108">**PR_PROVIDER_DLL_NAME**在 **[服务提供程序]** 部分中指定。</span><span class="sxs-lookup"><span data-stu-id="af3b4-108">The **PR_PROVIDER_DLL_NAME** is specified in the **[Service Provider]** section.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="af3b4-109">预期是设置提供程序的 .dll 的名称 (不带后缀 "32")。</span><span class="sxs-lookup"><span data-stu-id="af3b4-109">The expectation is that you set the name of your provider's .dll (without the suffix "32").</span></span> <span data-ttu-id="af3b4-110">然后, MAPI 将通过在路径上查找提供程序来加载提供程序。</span><span class="sxs-lookup"><span data-stu-id="af3b4-110">MAPI then loads your provider by looking for it on the path.</span></span> 
  
## <a name="putting-a-path-in-mapisvcinf"></a><span data-ttu-id="af3b4-111">在 mapisvc.inf 中放置路径</span><span class="sxs-lookup"><span data-stu-id="af3b4-111">Putting a Path in MapiSvc.inf</span></span>

<span data-ttu-id="af3b4-112">大多数应用程序都是在 "程序文件" 下安装的, 需要更新路径变量以允许 MAPI 提供程序正常工作。</span><span class="sxs-lookup"><span data-stu-id="af3b4-112">Most applications install under Program Files, requiring an update to the path variable to allow MAPI providers to work.</span></span> <span data-ttu-id="af3b4-113">通过一些限制, Microsoft Outlook 2010 和 Outlook 2013 可以容纳 MAPI 提供程序的完整路径。</span><span class="sxs-lookup"><span data-stu-id="af3b4-113">With a few restrictions Microsoft Outlook 2010 and Outlook 2013 can accommodate full paths to MAPI providers.</span></span>
  
<span data-ttu-id="af3b4-114">在 mapisvc.inf 中注册提供程序时, 可以在 MAPI 属性**PR_SERVICE_DLL_NAME**和**PR_PROVIDER_DLL_NAME**中添加提供程序的完整路径。</span><span class="sxs-lookup"><span data-stu-id="af3b4-114">When registering your provider in MapiSvc.inf, you could put the full path to the provider in the MAPI properties **PR_SERVICE_DLL_NAME** and **PR_PROVIDER_DLL_NAME**.</span></span>
  
<span data-ttu-id="af3b4-115">在这两个属性中, 完整路径必须不带后缀 "32", 因为 MAPI 继续在查找文件之前将其追加到文件名。</span><span class="sxs-lookup"><span data-stu-id="af3b4-115">In either property, the full path must be without the suffix "32", because MAPI continues to append that to the filename before looking for your file.</span></span> <span data-ttu-id="af3b4-116">这意味着, 如果注册路径 "c:\mypath\myprovider.dll", MAPI 将尝试加载 "c:\mypath\myprovider32.dll"。</span><span class="sxs-lookup"><span data-stu-id="af3b4-116">This means that if you register the path "c:\mypath\myprovider.dll", MAPI will attempt to load "c:\mypath\myprovider32.dll".</span></span>
  
<span data-ttu-id="af3b4-117">由于 Outlook 的 MAPI 最初并不是为了容纳完整路径而设计的, 因此, 通过查找字符串中的第一个句点 (这意味着包含其他句点的路径不起作用) 来完成此插入 "32" 后缀, 因此不能使用类似路径, 如"c:\my.path\myprovider.dll" 或 "c:\mypath\my.provider.dll"。</span><span class="sxs-lookup"><span data-stu-id="af3b4-117">Because Outlook's MAPI was not originally designed to accommodate full paths, it accomplishes this insertion of the "32" suffix by looking for the first period in the string, which means that paths that contain other periods cannot work, so you cannot use paths such as "c:\my.path\myprovider.dll" or "c:\mypath\my.provider.dll".</span></span>
  
<span data-ttu-id="af3b4-118">有时, 在存储提供程序中, 您将使用**WrapStoreEntryID**函数生成条目标识符, 该函数接受提供程序的名称作为参数。</span><span class="sxs-lookup"><span data-stu-id="af3b4-118">Sometimes in a store provider you will generate entry identifiers using the **WrapStoreEntryID** function, which takes as a parameter the name of your provider.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="af3b4-119">如果在 mapisvc.inf 中使用了完整路径, 则必须在对**WrapStoreEntryID**的任何调用中使用相同的路径。</span><span class="sxs-lookup"><span data-stu-id="af3b4-119">If you are using full paths in MapiSvc.inf, you must use the same path in any calls to **WrapStoreEntryID**.</span></span> 
  
<span data-ttu-id="af3b4-120">此外, 您使用的路径可以使用[GetACP](https://msdn.microsoft.com/library/windows/desktop/dd318070%28v=vs.85%29.aspx/)函数提供的代码页在 Unicode 和 Unicode 之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="af3b4-120">Additionally, the path you use may be converted to and from Unicode using the code page provided by the [GetACP](https://msdn.microsoft.com/library/windows/desktop/dd318070%28v=vs.85%29.aspx/) function.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="af3b4-121">如果您选择的路径包含无法在[MultiByteToWideChar](https://msdn.microsoft.com/library/windows/desktop/dd319072%28v=vs.85%29.aspx/)和[WideCharToMultiByte](https://msdn.microsoft.com/library/windows/desktop/dd374130%28v=vs.85%29.aspx/)函数中使用的字符, 则会遇到故障。</span><span class="sxs-lookup"><span data-stu-id="af3b4-121">You will experience failure if you choose a path that contains characters that cannot survive such a roundtrip through the [MultiByteToWideChar](https://msdn.microsoft.com/library/windows/desktop/dd319072%28v=vs.85%29.aspx/) and [WideCharToMultiByte](https://msdn.microsoft.com/library/windows/desktop/dd374130%28v=vs.85%29.aspx/) functions.</span></span> 
  
<span data-ttu-id="af3b4-122">有关此功能的演示, 已修订 GitHub 上的[包装 PST 示例](https://github.com/stephenegriffin/Outlook2010CodeSamples)-相关功能位于**MergeWithMapiSvc**和**GenerateProviderPath**中。</span><span class="sxs-lookup"><span data-stu-id="af3b4-122">For a demonstration of this functionality, the [Wrapped PST sample](https://github.com/stephenegriffin/Outlook2010CodeSamples) on GitHub has been revised - the pertinent functionality is in **MergeWithMapiSvc** and **GenerateProviderPath**.</span></span>
  

