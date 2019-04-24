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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2f0f1fb94ea36512bbc40df8a4877e89d2613a25
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309980"
---
# <a name="imsgserviceadminrenamemsgservice"></a><span data-ttu-id="f6b9e-103">IMsgServiceAdmin::RenameMsgService</span><span class="sxs-lookup"><span data-stu-id="f6b9e-103">IMsgServiceAdmin::RenameMsgService</span></span>

  
  
<span data-ttu-id="f6b9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6b9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6b9e-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-105">Deprecated.</span></span> <span data-ttu-id="f6b9e-106">为邮件服务分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-106">Assigns a new name to a message service.</span></span> 
  
```cpp
HRESULT RenameMsgService(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPSTR lpszDisplayName
);
```

## <a name="parameters"></a><span data-ttu-id="f6b9e-107">参数</span><span class="sxs-lookup"><span data-stu-id="f6b9e-107">Parameters</span></span>

 <span data-ttu-id="f6b9e-108">_lpUID_</span><span class="sxs-lookup"><span data-stu-id="f6b9e-108">_lpUID_</span></span>
  
> <span data-ttu-id="f6b9e-109">实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要重命名的邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-109">[in] A pointer to the [MAPIUID](mapiuid.md) structure that contains the unique identifier for the message service to rename.</span></span> 
    
 <span data-ttu-id="f6b9e-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f6b9e-110">_ulFlags_</span></span>
  
> <span data-ttu-id="f6b9e-111">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-111">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="f6b9e-112">_lpszDisplayName_</span><span class="sxs-lookup"><span data-stu-id="f6b9e-112">_lpszDisplayName_</span></span>
  
> <span data-ttu-id="f6b9e-113">实时指向邮件服务的新名称的指针。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-113">[in] A pointer to the new name for the message service.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f6b9e-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f6b9e-114">Return value</span></span>

<span data-ttu-id="f6b9e-115">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f6b9e-115">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="f6b9e-116">MAPI 不支持重命名此邮件服务。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-116">MAPI does not support renaming this message service.</span></span> <span data-ttu-id="f6b9e-117">**RenameMsgService**始终返回此值。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-117">**RenameMsgService** always returns this value.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f6b9e-118">注解</span><span class="sxs-lookup"><span data-stu-id="f6b9e-118">Remarks</span></span>

<span data-ttu-id="f6b9e-119">若要将新名称分配给邮件服务, 客户端应使用邮件服务的**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-119">To assign a new name to a message service, clients should use the **PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) property of the message service.</span></span> <span data-ttu-id="f6b9e-120">邮件服务中的服务提供程序的名称存储在其**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="f6b9e-120">The names of service providers in a message service are stored in their **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f6b9e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b9e-121">See also</span></span>



[<span data-ttu-id="f6b9e-122">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="f6b9e-122">MAPIUID</span></span>](mapiuid.md)
  
[<span data-ttu-id="f6b9e-123">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f6b9e-123">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

