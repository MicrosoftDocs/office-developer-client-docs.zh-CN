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
ms.openlocfilehash: 85cfd219eb83592a4e01263caf5d6923db39e0cc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583783"
---
# <a name="nstserviceentry"></a><span data-ttu-id="a8c24-103">NSTServiceEntry</span><span class="sxs-lookup"><span data-stu-id="a8c24-103">NSTServiceEntry</span></span>

  
  
<span data-ttu-id="a8c24-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a8c24-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a8c24-105">消息服务入口点函数 MAPI 的存储提供程序作为 NST 存储环绕基于 PST 的本地存储区。</span><span class="sxs-lookup"><span data-stu-id="a8c24-105">Message service entry point function for a MAPI store provider to wrap a PST-based local store as an NST store.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="a8c24-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="a8c24-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a8c24-107">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a8c24-107">Implemented by:</span></span>  <br/> |<span data-ttu-id="a8c24-108">MAPI 提供程序</span><span class="sxs-lookup"><span data-stu-id="a8c24-108">MAPI provider</span></span>  <br/> |
|<span data-ttu-id="a8c24-109">调用：</span><span class="sxs-lookup"><span data-stu-id="a8c24-109">Called by:</span></span>  <br/> |<span data-ttu-id="a8c24-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="a8c24-110">MAPI</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="a8c24-111">参数</span><span class="sxs-lookup"><span data-stu-id="a8c24-111">Parameters</span></span>

 <span data-ttu-id="a8c24-112">**NSTServiceEntry**使用**[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。</span><span class="sxs-lookup"><span data-stu-id="a8c24-112">**NSTServiceEntry** uses the **[MSGSERVICEENTRY](msgserviceentry.md)** function prototype.</span></span> <span data-ttu-id="a8c24-113">其参数信息，请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。</span><span class="sxs-lookup"><span data-stu-id="a8c24-113">For information on its parameters, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="return-values"></a><span data-ttu-id="a8c24-114">返回值</span><span class="sxs-lookup"><span data-stu-id="a8c24-114">Return values</span></span>

<span data-ttu-id="a8c24-115">返回值的信息，请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。</span><span class="sxs-lookup"><span data-stu-id="a8c24-115">For information on return values, see **[MSGSERVICEENTRY](msgserviceentry.md)**.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a8c24-116">注解</span><span class="sxs-lookup"><span data-stu-id="a8c24-116">Remarks</span></span>

<span data-ttu-id="a8c24-117">当使用**[GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx)** 查找 msmapi32.dll 中此函数的地址，指定"NSTServiceEntry"作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="a8c24-117">When using **[GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx)** to look for the address of this function in msmapi32.dll, specify "NSTServiceEntry" as the procedure name.</span></span> 
  
<span data-ttu-id="a8c24-118">若要使用复制 API，MAPI 存储提供程序必须首先打开并通过调用**[NSTServiceEntry](nstserviceentry.md)** 环绕基于 PST 的本地存储区。</span><span class="sxs-lookup"><span data-stu-id="a8c24-118">To use the Replication API, a MAPI store provider must first open and wrap a PST-based local store by calling **[NSTServiceEntry](nstserviceentry.md)**.</span></span> <span data-ttu-id="a8c24-119">提供程序然后可以使用 API、 **[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。</span><span class="sxs-lookup"><span data-stu-id="a8c24-119">The provider can then use the major interfaces of the API, **[IOSTX](iostxiunknown.md)** and **[IPSTX](ipstxiunknown.md)**, to carry out replication.</span></span> 
  
<span data-ttu-id="a8c24-120">下列说明适用于 NST 存储：</span><span class="sxs-lookup"><span data-stu-id="a8c24-120">The following remarks apply to an NST store:</span></span>
  
- <span data-ttu-id="a8c24-121">实现使用**NSTServiceEntry**MAPI 提供程序时，不要在全局配置文件部分中存储的任何信息。</span><span class="sxs-lookup"><span data-stu-id="a8c24-121">Do not store any information in the global profile section when implementing a MAPI provider that uses **NSTServiceEntry**.</span></span> <span data-ttu-id="a8c24-122">由多个提供程序共享全局配置文件部分，可以覆盖此配置文件中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="a8c24-122">The global profile section is shared by many providers and data stored in this profile can be overwritten.</span></span> 
    
- <span data-ttu-id="a8c24-123">仅当项目具有现有的修改时间戳获取其戳更新时对其进行保存。</span><span class="sxs-lookup"><span data-stu-id="a8c24-123">Only items with existing modification time stamps get their stamps updated when they are saved.</span></span> 
    
- <span data-ttu-id="a8c24-124">冲突检查不会发生自动保存项目时。</span><span class="sxs-lookup"><span data-stu-id="a8c24-124">Conflict-checking does not occur automatically when items are saved.</span></span>
    
-  <span data-ttu-id="a8c24-125">保存项目时，就不会发生重复检测。</span><span class="sxs-lookup"><span data-stu-id="a8c24-125">Duplicate detection does not occur when items are saved.</span></span> 
    
-  <span data-ttu-id="a8c24-126">附加表示缓存的版本的服务器的文件。NST。</span><span class="sxs-lookup"><span data-stu-id="a8c24-126">The file representing the cached version of the server is appended with .NST.</span></span> 
    
- <span data-ttu-id="a8c24-127">若要获得一个指向全局配置文件部分，消息服务时，可调用**[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 支持对象使用**pbNSTGlobalProfileSectionGuid** ，按如下：</span><span class="sxs-lookup"><span data-stu-id="a8c24-127">To obtain a pointer to the global profile section, a message service calls **[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** in the support object using **pbNSTGlobalProfileSectionGuid** as defined below:</span></span> 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- <span data-ttu-id="a8c24-128">在这种情况下，消息服务的支持对象应确保**IMAPISupport::OpenProfileSection**返回默认配置文件一节中的**[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性由配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="a8c24-128">In this case, the support object of the message service should ensure that **IMAPISupport::OpenProfileSection** returns the profile section that is identified by the **[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** property in the default profile section.</span></span> <span data-ttu-id="a8c24-129">若要获取此配置文件一节，支持对象可以打开默认配置文件部分，检索**PR_SERVICE_UID**，并将结果传递给**IMAPISupport::OpenProfileSection**检索正确的全局配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="a8c24-129">To get this profile section, the support object can open the default profile section, retrieve **PR_SERVICE_UID**, and pass the result to **IMAPISupport::OpenProfileSection** to retrieve the correct global profile section.</span></span> <span data-ttu-id="a8c24-130">支持对象又返回到邮件服务全局配置文件本节指针。</span><span class="sxs-lookup"><span data-stu-id="a8c24-130">The support object in turn returns a pointer to this global profile section to the message service.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a8c24-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8c24-131">See also</span></span>



[<span data-ttu-id="a8c24-132">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="a8c24-132">About the Replication API</span></span>](about-the-replication-api.md)

