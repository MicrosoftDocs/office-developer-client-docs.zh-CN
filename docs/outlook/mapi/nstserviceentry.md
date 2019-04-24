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
# <a name="nstserviceentry"></a><span data-ttu-id="b873d-103">NSTServiceEntry</span><span class="sxs-lookup"><span data-stu-id="b873d-103">NSTServiceEntry</span></span>

  
  
<span data-ttu-id="b873d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b873d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b873d-105">MAPI 存储提供程序的邮件服务入口点函数, 用于将基于 PST 的本地存储包装为 NST 存储。</span><span class="sxs-lookup"><span data-stu-id="b873d-105">Message service entry point function for a MAPI store provider to wrap a PST-based local store as an NST store.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="b873d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b873d-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b873d-107">实现者：</span><span class="sxs-lookup"><span data-stu-id="b873d-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="b873d-108">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="b873d-108">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="b873d-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="b873d-109">Called by:</span></span>  <br/> |<span data-ttu-id="b873d-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="b873d-110">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="b873d-111">参数</span><span class="sxs-lookup"><span data-stu-id="b873d-111">Parameters</span></span>

 <span data-ttu-id="b873d-112">**NSTServiceEntry**使用**[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。</span><span class="sxs-lookup"><span data-stu-id="b873d-112">**NSTServiceEntry** uses the **[MSGSERVICEENTRY](msgserviceentry.md)** function prototype.</span></span> <span data-ttu-id="b873d-113">有关其参数的信息, 请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。</span><span class="sxs-lookup"><span data-stu-id="b873d-113">For information on its parameters, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="return-values"></a><span data-ttu-id="b873d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="b873d-114">Return values</span></span>

<span data-ttu-id="b873d-115">有关返回值的信息, 请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。</span><span class="sxs-lookup"><span data-stu-id="b873d-115">For information on return values, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b873d-116">注解</span><span class="sxs-lookup"><span data-stu-id="b873d-116">Remarks</span></span>

<span data-ttu-id="b873d-117">使用**[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** 在 msmapi32 中查找此函数的地址时, 请将 "NSTServiceEntry" 指定为过程名称。</span><span class="sxs-lookup"><span data-stu-id="b873d-117">When using **[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** to look for the address of this function in msmapi32.dll, specify "NSTServiceEntry" as the procedure name.</span></span> 
  
<span data-ttu-id="b873d-118">若要使用复制 API, MAPI 存储提供程序必须先通过调用**[NSTServiceEntry](nstserviceentry.md)** 打开和包装基于 PST 的本地存储。</span><span class="sxs-lookup"><span data-stu-id="b873d-118">To use the Replication API, a MAPI store provider must first open and wrap a PST-based local store by calling **[NSTServiceEntry](nstserviceentry.md)**.</span></span> <span data-ttu-id="b873d-119">然后, 提供程序可以使用 API 的主要接口**[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 来执行复制。</span><span class="sxs-lookup"><span data-stu-id="b873d-119">The provider can then use the major interfaces of the API, **[IOSTX](iostxiunknown.md)** and **[IPSTX](ipstxiunknown.md)**, to carry out replication.</span></span> 
  
<span data-ttu-id="b873d-120">以下注释适用于 NST 存储:</span><span class="sxs-lookup"><span data-stu-id="b873d-120">The following remarks apply to an NST store:</span></span>
  
- <span data-ttu-id="b873d-121">在实现使用**NSTServiceEntry**的 MAPI 提供程序时, 请勿在全局配置文件部分中存储任何信息。</span><span class="sxs-lookup"><span data-stu-id="b873d-121">Do not store any information in the global profile section when implementing a MAPI provider that uses **NSTServiceEntry**.</span></span> <span data-ttu-id="b873d-122">全局配置文件部分由多个提供程序共享, 并且可以覆盖存储在此配置文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="b873d-122">The global profile section is shared by many providers and data stored in this profile can be overwritten.</span></span> 
    
- <span data-ttu-id="b873d-123">在保存时, 只有具有现有修改时间戳的项目会更新其图章。</span><span class="sxs-lookup"><span data-stu-id="b873d-123">Only items with existing modification time stamps get their stamps updated when they are saved.</span></span> 
    
- <span data-ttu-id="b873d-124">冲突-在保存项目时不会自动进行检查。</span><span class="sxs-lookup"><span data-stu-id="b873d-124">Conflict-checking does not occur automatically when items are saved.</span></span>
    
-  <span data-ttu-id="b873d-125">保存项目时不会进行重复检测。</span><span class="sxs-lookup"><span data-stu-id="b873d-125">Duplicate detection does not occur when items are saved.</span></span> 
    
-  <span data-ttu-id="b873d-126">附加了表示服务器的缓存版本的文件。NST.</span><span class="sxs-lookup"><span data-stu-id="b873d-126">The file representing the cached version of the server is appended with .NST.</span></span> 
    
- <span data-ttu-id="b873d-127">若要获取指向 "全局配置文件" 部分的指针, 邮件服务将使用以下定义的**pbNSTGlobalProfileSectionGuid**在支持对象中调用**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** :</span><span class="sxs-lookup"><span data-stu-id="b873d-127">To obtain a pointer to the global profile section, a message service calls **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** in the support object using **pbNSTGlobalProfileSectionGuid** as defined below:</span></span> 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- <span data-ttu-id="b873d-128">在这种情况下, 邮件服务的支持对象应确保**IMAPISupport:: OpenProfileSection**返回由 "默认配置文件" 部分中的**[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性标识的 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="b873d-128">In this case, the support object of the message service should ensure that **IMAPISupport::OpenProfileSection** returns the profile section that is identified by the **[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** property in the default profile section.</span></span> <span data-ttu-id="b873d-129">若要获取此配置文件部分, 支持对象可以打开默认的配置文件部分, 检索**PR_SERVICE_UID**, 并将结果传递给**IMAPISupport:: OpenProfileSection**以检索正确的全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="b873d-129">To get this profile section, the support object can open the default profile section, retrieve **PR_SERVICE_UID**, and pass the result to **IMAPISupport::OpenProfileSection** to retrieve the correct global profile section.</span></span> <span data-ttu-id="b873d-130">支持对象反过来又将指向此全局配置文件部分的指针返回到邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b873d-130">The support object in turn returns a pointer to this global profile section to the message service.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b873d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b873d-131">See also</span></span>



[<span data-ttu-id="b873d-132">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="b873d-132">About the Replication API</span></span>](about-the-replication-api.md)

