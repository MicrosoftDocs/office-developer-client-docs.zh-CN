---
title: MapiSvc.inf 中注册服务和服务提供商
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a04acf17-4b2d-458e-9852-b6074acac096
description: 上次修改时间： 2013 年 7 月 18 日
ms.openlocfilehash: 2eb7f1b496e0732b157ea4f9105a0e067329c52f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778605"
---
# <a name="registering-services-and-service-providers-in-mapisvcinf"></a><span data-ttu-id="b4763-103">MapiSvc.inf 中注册服务和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b4763-103">Registering Services and Service Providers in MapiSvc.inf</span></span>

 
  
<span data-ttu-id="b4763-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b4763-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b4763-105">系统上安装新的提供程序需要更新 MapiSvc.inf 文件以指向新的提供程序。</span><span class="sxs-lookup"><span data-stu-id="b4763-105">Installing a new provider on a system requires updating the MapiSvc.inf file to point to the new provider.</span></span> <span data-ttu-id="b4763-106">标准属性设置在配置期间，其中包括以下，告知 MAPI 在哪里可以找到提供程序的动态链接库 (.dll):</span><span class="sxs-lookup"><span data-stu-id="b4763-106">Standard properties set during configuration, which include the following, inform MAPI where to find the provider's dynamic-link library (.dll):</span></span>
  
- <span data-ttu-id="b4763-107">在 **[消息服务]** 部分中指定**PR_SERVICE_DLL_NAME** 。</span><span class="sxs-lookup"><span data-stu-id="b4763-107">The **PR_SERVICE_DLL_NAME** is specified in the **[Message Service]** section.</span></span> 
    
- <span data-ttu-id="b4763-108">**PR_PROVIDER_DLL_NAME** **[服务提供商]** 节中指定。</span><span class="sxs-lookup"><span data-stu-id="b4763-108">The **PR_PROVIDER_DLL_NAME** is specified in the **[Service Provider]** section.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b4763-109">预期结果是.dll 的您设置提供程序 （而不使用后缀"32"） 的名称。</span><span class="sxs-lookup"><span data-stu-id="b4763-109">The expectation is that you set the name of your provider's .dll (without the suffix "32").</span></span> <span data-ttu-id="b4763-110">MAPI 然后通过路径上查找加载您的提供商。</span><span class="sxs-lookup"><span data-stu-id="b4763-110">MAPI then loads your provider by looking for it on the path.</span></span> 
  
## <a name="putting-a-path-in-mapisvcinf"></a><span data-ttu-id="b4763-111">将路径放在 MapiSvc.inf</span><span class="sxs-lookup"><span data-stu-id="b4763-111">Putting a Path in MapiSvc.inf</span></span>

<span data-ttu-id="b4763-112">大多数应用程序安装在 Program Files，需要更新到 path 变量以允许 MAPI 提供程序工作下。</span><span class="sxs-lookup"><span data-stu-id="b4763-112">Most applications install under Program Files, requiring an update to the path variable to allow MAPI providers to work.</span></span> <span data-ttu-id="b4763-113">一些限制与 Microsoft Outlook 2010 和 Outlook 2013 可以适应到 MAPI 提供程序的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b4763-113">With a few restrictions Microsoft Outlook 2010 and Outlook 2013 can accommodate full paths to MAPI providers.</span></span>
  
<span data-ttu-id="b4763-114">时在 MapiSvc.inf 注册提供程序，您无法 MAPI 属性**PR_SERVICE_DLL_NAME**和**PR_PROVIDER_DLL_NAME**中提供程序将的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b4763-114">When registering your provider in MapiSvc.inf, you could put the full path to the provider in the MAPI properties **PR_SERVICE_DLL_NAME** and **PR_PROVIDER_DLL_NAME**.</span></span>
  
<span data-ttu-id="b4763-115">在这两个属性的完整路径必须是不带后缀"32"中，因为 MAPI 继续追加到文件名查找您的文件之前。</span><span class="sxs-lookup"><span data-stu-id="b4763-115">In either property, the full path must be without the suffix "32", because MAPI continues to append that to the filename before looking for your file.</span></span> <span data-ttu-id="b4763-116">这意味着，如果您注册"c:\mypath\myprovider.dll"的路径，MAPI 将尝试加载"c:\mypath\myprovider32.dll"。</span><span class="sxs-lookup"><span data-stu-id="b4763-116">This means that if you register the path "c:\mypath\myprovider.dll", MAPI will attempt to load "c:\mypath\myprovider32.dll".</span></span>
  
<span data-ttu-id="b4763-117">由于 Outlook 的 MAPI 未最初设计以适应完整路径，它通过查看在字符串中，这意味着，包含其他句点的路径不能工作，因此您不能使用路径，如的第一段完成的"32"后缀此插入"c:\my.path\myprovider.dll"或者"c:\mypath\my.provider.dll"。</span><span class="sxs-lookup"><span data-stu-id="b4763-117">Because Outlook's MAPI was not originally designed to accommodate full paths, it accomplishes this insertion of the "32" suffix by looking for the first period in the string, which means that paths that contain other periods cannot work, so you cannot use paths such as "c:\my.path\myprovider.dll" or "c:\mypath\my.provider.dll".</span></span>
  
<span data-ttu-id="b4763-118">有时的存储提供程序中将生成使用**WrapStoreEntryID**函数，它提供程序名称作为参数采用项标识符。</span><span class="sxs-lookup"><span data-stu-id="b4763-118">Sometimes in a store provider you will generate entry identifiers using the **WrapStoreEntryID** function, which takes as a parameter the name of your provider.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b4763-119">如果您在 MapiSvc.inf 中使用完整路径，您必须**WrapStoreEntryID**调用中使用同一个路径。</span><span class="sxs-lookup"><span data-stu-id="b4763-119">If you are using full paths in MapiSvc.inf, you must use the same path in any calls to **WrapStoreEntryID**.</span></span> 
  
<span data-ttu-id="b4763-120">此外，可能会与 Unicode 使用供稿[GetACP](http://msdn.microsoft.com/en-us/library/windows/desktop/dd318070%28v=vs.85%29.aspx/)函数的代码页转换您使用的路径。</span><span class="sxs-lookup"><span data-stu-id="b4763-120">Additionally, the path you use may be converted to and from Unicode using the code page provided by the [GetACP](http://msdn.microsoft.com/en-us/library/windows/desktop/dd318070%28v=vs.85%29.aspx/) function.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b4763-121">如果您选择包含不能排除通过[MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/windows/desktop/dd319072%28v=vs.85%29.aspx/)和[WideCharToMultiByte](http://msdn.microsoft.com/en-us/library/windows/desktop/dd374130%28v=vs.85%29.aspx/)函数此类的往返行程的字符的路径，则会出现故障。</span><span class="sxs-lookup"><span data-stu-id="b4763-121">You will experience failure if you choose a path that contains characters that cannot survive such a roundtrip through the [MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/windows/desktop/dd319072%28v=vs.85%29.aspx/) and [WideCharToMultiByte](http://msdn.microsoft.com/en-us/library/windows/desktop/dd374130%28v=vs.85%29.aspx/) functions.</span></span> 
  
<span data-ttu-id="b4763-122">此功能的演示，CodePlex 上的[自动换行 PST 示例](http://ol2010mapisamples.codeplex.com/)已经过修改-相关的功能是**MergeWithMapiSvc**和**GenerateProviderPath**中。</span><span class="sxs-lookup"><span data-stu-id="b4763-122">For a demonstration of this functionality, the [Wrapped PST sample](http://ol2010mapisamples.codeplex.com/) on CodePlex has been revised - the pertinent functionality is in **MergeWithMapiSvc** and **GenerateProviderPath**.</span></span>
  

