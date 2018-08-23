---
title: IMsgServiceAdminRenameMsgService
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.RenameMsgService
api_type:
- COM
ms.assetid: eba0e7f2-03c1-4713-aa36-3d0b398cd197
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a6eba20fb346f53052808abf8fcae8993d423d34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589558"
---
# <a name="imsgserviceadminrenamemsgservice"></a><span data-ttu-id="a0804-103">IMsgServiceAdmin::RenameMsgService</span><span class="sxs-lookup"><span data-stu-id="a0804-103">IMsgServiceAdmin::RenameMsgService</span></span>

  
  
<span data-ttu-id="a0804-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0804-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0804-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="a0804-105">Deprecated.</span></span> <span data-ttu-id="a0804-106">将新的名称分配给邮件服务。</span><span class="sxs-lookup"><span data-stu-id="a0804-106">Assigns a new name to a message service.</span></span> 
  
```cpp
HRESULT RenameMsgService(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPSTR lpszDisplayName
);
```

## <a name="parameters"></a><span data-ttu-id="a0804-107">参数</span><span class="sxs-lookup"><span data-stu-id="a0804-107">Parameters</span></span>

 <span data-ttu-id="a0804-108">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="a0804-108">_lpUID_</span></span>
  
> <span data-ttu-id="a0804-109">[in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要重命名的消息服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a0804-109">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to rename.</span></span> 
    
 <span data-ttu-id="a0804-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a0804-110">_ulFlags_</span></span>
  
> <span data-ttu-id="a0804-111">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="a0804-111">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="a0804-112">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="a0804-112">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="a0804-113">[in]一个指向邮件服务的新名称。</span><span class="sxs-lookup"><span data-stu-id="a0804-113">[in] A pointer to the new name for the message service.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a0804-114">返回值</span><span class="sxs-lookup"><span data-stu-id="a0804-114">Return value</span></span>

<span data-ttu-id="a0804-115">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="a0804-115">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="a0804-116">MAPI 不支持重命名此消息服务。</span><span class="sxs-lookup"><span data-stu-id="a0804-116">MAPI does not support renaming this message service.</span></span> <span data-ttu-id="a0804-117">**RenameMsgService**始终返回此值。</span><span class="sxs-lookup"><span data-stu-id="a0804-117">**RenameMsgService** always returns this value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a0804-118">注解</span><span class="sxs-lookup"><span data-stu-id="a0804-118">Remarks</span></span>

<span data-ttu-id="a0804-119">分配给消息服务的新名称，客户端应使用消息服务的**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a0804-119">To assign a new name to a message service, clients should use the **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) property of the message service.</span></span> <span data-ttu-id="a0804-120">消息服务中的服务提供商的名称将存储在其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a0804-120">The names of service providers in a message service are stored in their **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a0804-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0804-121">See also</span></span>



[<span data-ttu-id="a0804-122">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="a0804-122">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="a0804-123">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a0804-123">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

