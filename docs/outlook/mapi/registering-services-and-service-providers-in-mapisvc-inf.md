---
title: 在 MapiSvc.inf 中注册服务和服务提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a04acf17-4b2d-458e-9852-b6074acac096
description: 上次修改时间：2013 年 7 月 18 日
ms.openlocfilehash: adc6318ab36818b4c423bb6b1dc1b083b3fb54eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328369"
---
# <a name="registering-services-and-service-providers-in-mapisvcinf"></a><span data-ttu-id="e6640-103">在 MapiSvc.inf 中注册服务和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="e6640-103">Registering Services and Service Providers in MapiSvc.inf</span></span>

 
  
<span data-ttu-id="e6640-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6640-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6640-105">在系统上安装新提供程序需要更新 MapiSvc.inf 文件以指向新提供程序。</span><span class="sxs-lookup"><span data-stu-id="e6640-105">Installing a new provider on a system requires updating the MapiSvc.inf file to point to the new provider.</span></span> <span data-ttu-id="e6640-106">在配置过程中设置的标准属性（包括以下内容）会通知 MAPI 在何处查找提供程序的动态链接库 (.dll) ：</span><span class="sxs-lookup"><span data-stu-id="e6640-106">Standard properties set during configuration, which include the following, inform MAPI where to find the provider's dynamic-link library (.dll):</span></span>
  
- <span data-ttu-id="e6640-107">The **PR_SERVICE_DLL_NAME** is specified in the **[Message Service]** section.</span><span class="sxs-lookup"><span data-stu-id="e6640-107">The **PR_SERVICE_DLL_NAME** is specified in the **[Message Service]** section.</span></span> 
    
- <span data-ttu-id="e6640-108">The **PR_PROVIDER_DLL_NAME** is specified in the **[Service Provider]** section.</span><span class="sxs-lookup"><span data-stu-id="e6640-108">The **PR_PROVIDER_DLL_NAME** is specified in the **[Service Provider]** section.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="e6640-109">预期是设置提供程序的名称，.dll (后缀"32") 。</span><span class="sxs-lookup"><span data-stu-id="e6640-109">The expectation is that you set the name of your provider's .dll (without the suffix "32").</span></span> <span data-ttu-id="e6640-110">然后，MAPI 通过查找路径来加载提供程序。</span><span class="sxs-lookup"><span data-stu-id="e6640-110">MAPI then loads your provider by looking for it on the path.</span></span> 
  
## <a name="putting-a-path-in-mapisvcinf"></a><span data-ttu-id="e6640-111">在 MapiSvc.inf 中放置路径</span><span class="sxs-lookup"><span data-stu-id="e6640-111">Putting a Path in MapiSvc.inf</span></span>

<span data-ttu-id="e6640-112">大多数应用程序都安装在 Program Files 下，需要更新路径变量以允许 MAPI 提供程序工作。</span><span class="sxs-lookup"><span data-stu-id="e6640-112">Most applications install under Program Files, requiring an update to the path variable to allow MAPI providers to work.</span></span> <span data-ttu-id="e6640-113">在 2013 Microsoft Outlook 2010和 2013 Outlook可以容纳 MAPI 提供程序的完整路径。</span><span class="sxs-lookup"><span data-stu-id="e6640-113">With a few restrictions Microsoft Outlook 2010 and Outlook 2013 can accommodate full paths to MAPI providers.</span></span>
  
<span data-ttu-id="e6640-114">在 MapiSvc.inf 中注册提供程序时，可以在 MAPI 属性中放入提供程序的完整路径PR_SERVICE_DLL_NAME **PR_PROVIDER_DLL_NAME** **。**</span><span class="sxs-lookup"><span data-stu-id="e6640-114">When registering your provider in MapiSvc.inf, you could put the full path to the provider in the MAPI properties **PR_SERVICE_DLL_NAME** and **PR_PROVIDER_DLL_NAME**.</span></span>
  
<span data-ttu-id="e6640-115">在任一属性中，完整路径都必须没有后缀"32"，因为 MAPI 将继续在查找文件之前将该文件追加到文件名。</span><span class="sxs-lookup"><span data-stu-id="e6640-115">In either property, the full path must be without the suffix "32", because MAPI continues to append that to the filename before looking for your file.</span></span> <span data-ttu-id="e6640-116">这意味着，如果注册路径"c:\mypath\myprovider.dll"，MAPI 将尝试加载"c:\mypath\myprovider32.dll"。</span><span class="sxs-lookup"><span data-stu-id="e6640-116">This means that if you register the path "c:\mypath\myprovider.dll", MAPI will attempt to load "c:\mypath\myprovider32.dll".</span></span>
  
<span data-ttu-id="e6640-117">由于 Outlook 的 MAPI 最初并非旨在容纳完整路径，因此它通过查找字符串中的第一个句点（这意味着包含其他句点的路径无法工作）完成"32"后缀的插入，因此不能使用"c:\my.path\myprovider.dll"或"c:\mypath\my.provider.dll"等路径。</span><span class="sxs-lookup"><span data-stu-id="e6640-117">Because Outlook's MAPI was not originally designed to accommodate full paths, it accomplishes this insertion of the "32" suffix by looking for the first period in the string, which means that paths that contain other periods cannot work, so you cannot use paths such as "c:\my.path\myprovider.dll" or "c:\mypath\my.provider.dll".</span></span>
  
<span data-ttu-id="e6640-118">有时在存储提供程序中，你将使用 **WrapStoreEntryID** 函数生成条目标识符，该函数将提供程序的名称作为参数。</span><span class="sxs-lookup"><span data-stu-id="e6640-118">Sometimes in a store provider you will generate entry identifiers using the **WrapStoreEntryID** function, which takes as a parameter the name of your provider.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e6640-119">如果在 MapiSvc.inf 中使用的是完整路径，则必须在调用 **WrapStoreEntryID** 时使用相同的路径。</span><span class="sxs-lookup"><span data-stu-id="e6640-119">If you are using full paths in MapiSvc.inf, you must use the same path in any calls to **WrapStoreEntryID**.</span></span> 
  
<span data-ttu-id="e6640-120">此外，可以使用 [GetACP](https://msdn.microsoft.com/library/windows/desktop/dd318070%28v=vs.85%29.aspx/) 函数提供的代码页，将你使用的路径转换为 Unicode，也可以从 Unicode 转换路径。</span><span class="sxs-lookup"><span data-stu-id="e6640-120">Additionally, the path you use may be converted to and from Unicode using the code page provided by the [GetACP](https://msdn.microsoft.com/library/windows/desktop/dd318070%28v=vs.85%29.aspx/) function.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e6640-121">如果选择的路径包含无法通过 [MultiByteToWideChar](https://msdn.microsoft.com/library/windows/desktop/dd319072%28v=vs.85%29.aspx/) 和 [WideCharToMultiByte](https://msdn.microsoft.com/library/windows/desktop/dd374130%28v=vs.85%29.aspx/) 函数在此类往返中保留的字符，则您将遇到失败。</span><span class="sxs-lookup"><span data-stu-id="e6640-121">You will experience failure if you choose a path that contains characters that cannot survive such a roundtrip through the [MultiByteToWideChar](https://msdn.microsoft.com/library/windows/desktop/dd319072%28v=vs.85%29.aspx/) and [WideCharToMultiByte](https://msdn.microsoft.com/library/windows/desktop/dd374130%28v=vs.85%29.aspx/) functions.</span></span> 
  
<span data-ttu-id="e6640-122">为了演示此功能，已修改 GitHub 上的封装 [PST](https://github.com/stephenegriffin/Outlook2010CodeSamples)示例 - 相关功能位于 **MergeWithMapiSvc** 和 **GenerateProviderPath** 中。</span><span class="sxs-lookup"><span data-stu-id="e6640-122">For a demonstration of this functionality, the [Wrapped PST sample](https://github.com/stephenegriffin/Outlook2010CodeSamples) on GitHub has been revised - the pertinent functionality is in **MergeWithMapiSvc** and **GenerateProviderPath**.</span></span>
  

