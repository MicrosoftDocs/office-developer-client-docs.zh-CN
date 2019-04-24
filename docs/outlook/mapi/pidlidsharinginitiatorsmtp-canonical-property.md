---
title: PidLidSharingInitiatorSmtp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingInitiatorSmtp
api_type:
- COM
ms.assetid: 4fb7d91d-4c51-41c1-9cb6-7b837dd12f11
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eb699b2312064f8ed330238962dd86992c046139
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337119"
---
# <a name="pidlidsharinginitiatorsmtp-canonical-property"></a><span data-ttu-id="08175-103">PidLidSharingInitiatorSmtp 规范属性</span><span class="sxs-lookup"><span data-stu-id="08175-103">PidLidSharingInitiatorSmtp Canonical Property</span></span>

  
  
<span data-ttu-id="08175-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08175-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08175-105">指定启动共享邮件的用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="08175-105">Specifies the SMTP address of the user who initiated the sharing message.</span></span> <span data-ttu-id="08175-106">这是共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="08175-106">This is a property of a sharing message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="08175-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="08175-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="08175-108">dispidSharingInitiatorSmtp</span><span class="sxs-lookup"><span data-stu-id="08175-108">dispidSharingInitiatorSmtp</span></span>  <br/> |
|<span data-ttu-id="08175-109">属性集:</span><span class="sxs-lookup"><span data-stu-id="08175-109">Property set:</span></span>  <br/> |<span data-ttu-id="08175-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="08175-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="08175-111">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="08175-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="08175-112">0x00008A08</span><span class="sxs-lookup"><span data-stu-id="08175-112">0x00008A08</span></span>  <br/> |
|<span data-ttu-id="08175-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="08175-113">Data type:</span></span>  <br/> |<span data-ttu-id="08175-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="08175-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="08175-115">区域：</span><span class="sxs-lookup"><span data-stu-id="08175-115">Area:</span></span>  <br/> |<span data-ttu-id="08175-116">共享</span><span class="sxs-lookup"><span data-stu-id="08175-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08175-117">注解</span><span class="sxs-lookup"><span data-stu-id="08175-117">Remarks</span></span>

<span data-ttu-id="08175-118">此属性必须设置为**dispidSharingInitiatorEid** ([PidLidSharingInitiatorEntryId](pidlidsharinginitiatorentryid-canonical-property.md)) 属性所标识的通讯簿中的**PR_SMTP_ADDRESS** ([PidTagSmtpAddress](pidtagsmtpaddress-canonical-property.md)) 属性的值, 并且应忽视.</span><span class="sxs-lookup"><span data-stu-id="08175-118">This property must be set to the value of the **PR_SMTP_ADDRESS** ([PidTagSmtpAddress](pidtagsmtpaddress-canonical-property.md)) property from the Address Book identified by the **dispidSharingInitiatorEid** ([PidLidSharingInitiatorEntryId](pidlidsharinginitiatorentryid-canonical-property.md)) property and should be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="08175-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="08175-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="08175-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="08175-120">Protocol specifications</span></span>

<span data-ttu-id="08175-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08175-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08175-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="08175-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="08175-123">[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08175-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08175-124">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="08175-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="08175-125">头文件</span><span class="sxs-lookup"><span data-stu-id="08175-125">Header files</span></span>

<span data-ttu-id="08175-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="08175-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="08175-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="08175-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="08175-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08175-128">See also</span></span>



[<span data-ttu-id="08175-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="08175-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="08175-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="08175-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="08175-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="08175-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="08175-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="08175-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

