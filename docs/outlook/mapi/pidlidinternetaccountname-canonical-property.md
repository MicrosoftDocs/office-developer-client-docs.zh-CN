---
title: PidLidInternetAccountName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidInternetAccountName
api_type:
- COM
ms.assetid: 29bedadf-903d-419d-804d-dc8bd92b745d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6705b121c58e0ff14726f835c779237cb35c32a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776872"
---
# <a name="pidlidinternetaccountname-canonical-property"></a><span data-ttu-id="703c8-103">PidLidInternetAccountName 规范属性</span><span class="sxs-lookup"><span data-stu-id="703c8-103">PidLidInternetAccountName Canonical Property</span></span>

  
  
<span data-ttu-id="703c8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="703c8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="703c8-105">指定通过其发送的电子邮件的用户可见的电子邮件帐户名称。</span><span class="sxs-lookup"><span data-stu-id="703c8-105">Specifies the user-visible email account name through which the email message is sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="703c8-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="703c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="703c8-107">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="703c8-107">dispidInetAcctName</span></span>  <br/> |
|<span data-ttu-id="703c8-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="703c8-108">Property set:</span></span>  <br/> |<span data-ttu-id="703c8-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="703c8-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="703c8-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="703c8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="703c8-111">0x00008580</span><span class="sxs-lookup"><span data-stu-id="703c8-111">0x00008580</span></span>  <br/> |
|<span data-ttu-id="703c8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="703c8-112">Data type:</span></span>  <br/> |<span data-ttu-id="703c8-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="703c8-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="703c8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="703c8-114">Area:</span></span>  <br/> |<span data-ttu-id="703c8-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="703c8-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="703c8-116">备注</span><span class="sxs-lookup"><span data-stu-id="703c8-116">Remarks</span></span>

<span data-ttu-id="703c8-117">此字符串的格式是实现相关。</span><span class="sxs-lookup"><span data-stu-id="703c8-117">The format of this string is implementation dependent.</span></span> <span data-ttu-id="703c8-118">此属性在客户端可以用于确定哪个服务器定向邮件到，但是可选的和值没有任何意义到服务器。</span><span class="sxs-lookup"><span data-stu-id="703c8-118">This property can be used by the client to determine which server to direct the mail to, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="703c8-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="703c8-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="703c8-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="703c8-120">Protocol specifications</span></span>

<span data-ttu-id="703c8-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="703c8-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="703c8-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="703c8-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="703c8-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="703c8-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="703c8-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="703c8-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="703c8-125">头文件</span><span class="sxs-lookup"><span data-stu-id="703c8-125">Header files</span></span>

<span data-ttu-id="703c8-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="703c8-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="703c8-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="703c8-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="703c8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="703c8-128">See also</span></span>



[<span data-ttu-id="703c8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="703c8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="703c8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="703c8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="703c8-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="703c8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="703c8-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="703c8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

