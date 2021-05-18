---
title: NSTServiceEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5ada6363-2406-4c0a-8326-a299a8bbefe1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96c04a242c477204ea1447fb78c31d189eeac59a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280052"
---
# <a name="nstserviceentry"></a><span data-ttu-id="29f14-103">NSTServiceEntry</span><span class="sxs-lookup"><span data-stu-id="29f14-103">NSTServiceEntry</span></span>

  
  
<span data-ttu-id="29f14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29f14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29f14-105">MAPI 存储提供程序的邮件服务入口点函数，用于将基于 PST 的本地存储包装为 NST 存储。</span><span class="sxs-lookup"><span data-stu-id="29f14-105">Message service entry point function for a MAPI store provider to wrap a PST-based local store as an NST store.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="29f14-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="29f14-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="29f14-107">实现者：</span><span class="sxs-lookup"><span data-stu-id="29f14-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="29f14-108">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="29f14-108">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="29f14-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="29f14-109">Called by:</span></span>  <br/> |<span data-ttu-id="29f14-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="29f14-110">MAPI</span></span>  <br/> |
   
```cpp
HRESULT NSTServiceEntry( 
    HINSTANCE hInstance,   
    LPMALLOC lpMalloc, 
    LPMAPISUP lpMAPISup, 
    ULONG ulUIParam, 
    ULONG ulFlags, 
    ULONG ulContext, 
    ULONG cValues, 
    LPSPropValue lpProps, 
    LPPROVIDERADMIN lpProviderAdmin, 
    LPMAPIERROR FAR * lppMapiError 
);
```

## <a name="parameters"></a><span data-ttu-id="29f14-111">参数</span><span class="sxs-lookup"><span data-stu-id="29f14-111">Parameters</span></span>

 <span data-ttu-id="29f14-112">**NSTServiceEntry** 使用 **[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。</span><span class="sxs-lookup"><span data-stu-id="29f14-112">**NSTServiceEntry** uses the **[MSGSERVICEENTRY](msgserviceentry.md)** function prototype.</span></span> <span data-ttu-id="29f14-113">有关其参数的信息，请参阅 **[MSGSERVICEENTRY。](msgserviceentry.md)**</span><span class="sxs-lookup"><span data-stu-id="29f14-113">For information on its parameters, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="return-values"></a><span data-ttu-id="29f14-114">返回值</span><span class="sxs-lookup"><span data-stu-id="29f14-114">Return values</span></span>

<span data-ttu-id="29f14-115">有关返回值的信息，请参阅 **[MSGSERVICEENTRY。](msgserviceentry.md)**</span><span class="sxs-lookup"><span data-stu-id="29f14-115">For information on return values, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="29f14-116">备注</span><span class="sxs-lookup"><span data-stu-id="29f14-116">Remarks</span></span>

<span data-ttu-id="29f14-117">使用 **[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** 在 msmapi32.dll 中查找此函数的地址时，请指定"NSTServiceEntry"作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="29f14-117">When using **[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** to look for the address of this function in msmapi32.dll, specify "NSTServiceEntry" as the procedure name.</span></span> 
  
<span data-ttu-id="29f14-118">若要使用复制 API，MAPI 存储提供程序必须先通过调用 **[NSTServiceEntry](nstserviceentry.md)** 打开并包装基于 PST 的本地存储。</span><span class="sxs-lookup"><span data-stu-id="29f14-118">To use the Replication API, a MAPI store provider must first open and wrap a PST-based local store by calling **[NSTServiceEntry](nstserviceentry.md)**.</span></span> <span data-ttu-id="29f14-119">然后，提供程序可以使用 **[API、IOSTX](iostxiunknown.md)** 和 **[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。</span><span class="sxs-lookup"><span data-stu-id="29f14-119">The provider can then use the major interfaces of the API, **[IOSTX](iostxiunknown.md)** and **[IPSTX](ipstxiunknown.md)**, to carry out replication.</span></span> 
  
<span data-ttu-id="29f14-120">以下备注适用于 NST 存储：</span><span class="sxs-lookup"><span data-stu-id="29f14-120">The following remarks apply to an NST store:</span></span>
  
- <span data-ttu-id="29f14-121">实现使用 **NSTServiceEntry** 的 MAPI 提供程序时，请不要在全局配置文件部分中存储任何信息。</span><span class="sxs-lookup"><span data-stu-id="29f14-121">Do not store any information in the global profile section when implementing a MAPI provider that uses **NSTServiceEntry**.</span></span> <span data-ttu-id="29f14-122">全局配置文件部分由多个提供程序共享，并且此配置文件中存储的数据可以覆盖。</span><span class="sxs-lookup"><span data-stu-id="29f14-122">The global profile section is shared by many providers and data stored in this profile can be overwritten.</span></span> 
    
- <span data-ttu-id="29f14-123">只有具有现有修改时间戳的项才能在保存时更新其标记。</span><span class="sxs-lookup"><span data-stu-id="29f14-123">Only items with existing modification time stamps get their stamps updated when they are saved.</span></span> 
    
- <span data-ttu-id="29f14-124">保存项目时不会自动进行冲突检查。</span><span class="sxs-lookup"><span data-stu-id="29f14-124">Conflict-checking does not occur automatically when items are saved.</span></span>
    
-  <span data-ttu-id="29f14-125">保存项目时不会发生重复检测。</span><span class="sxs-lookup"><span data-stu-id="29f14-125">Duplicate detection does not occur when items are saved.</span></span> 
    
-  <span data-ttu-id="29f14-126">表示服务器的缓存版本的文件附加有 。NST。</span><span class="sxs-lookup"><span data-stu-id="29f14-126">The file representing the cached version of the server is appended with .NST.</span></span> 
    
- <span data-ttu-id="29f14-127">若要获取指向全局配置文件节的指针，邮件服务使用 **pbNSTGlobalProfileSectionGuid** 调用支持对象中的 **[IMAPISupport：：OpenProfileSection，](imapisupport-openprofilesection.md)** 定义如下：</span><span class="sxs-lookup"><span data-stu-id="29f14-127">To obtain a pointer to the global profile section, a message service calls **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** in the support object using **pbNSTGlobalProfileSectionGuid** as defined below:</span></span> 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- <span data-ttu-id="29f14-128">在这种情况下，邮件服务的支持对象应确保 **IMAPISupport：：OpenProfileSection** 返回由默认配置文件部分中的 **[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性标识的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="29f14-128">In this case, the support object of the message service should ensure that **IMAPISupport::OpenProfileSection** returns the profile section that is identified by the **[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** property in the default profile section.</span></span> <span data-ttu-id="29f14-129">若要获取此配置文件部分，支持对象可以打开默认配置文件部分，检索 **PR_SERVICE_UID，** 将结果传递给 **IMAPISupport：：OpenProfileSection** 以检索正确的全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="29f14-129">To get this profile section, the support object can open the default profile section, retrieve **PR_SERVICE_UID**, and pass the result to **IMAPISupport::OpenProfileSection** to retrieve the correct global profile section.</span></span> <span data-ttu-id="29f14-130">反过来，支持对象会向邮件服务返回指向此全局配置文件节的指针。</span><span class="sxs-lookup"><span data-stu-id="29f14-130">The support object in turn returns a pointer to this global profile section to the message service.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="29f14-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29f14-131">See also</span></span>



[<span data-ttu-id="29f14-132">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="29f14-132">About the Replication API</span></span>](about-the-replication-api.md)

