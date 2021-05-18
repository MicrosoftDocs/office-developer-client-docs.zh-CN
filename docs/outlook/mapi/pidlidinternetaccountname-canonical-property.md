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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2da826fe7ab9e4d7ca3eaaf0f9806193c47100d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315489"
---
# <a name="pidlidinternetaccountname-canonical-property"></a><span data-ttu-id="7c84a-103">PidLidInternetAccountName 规范属性</span><span class="sxs-lookup"><span data-stu-id="7c84a-103">PidLidInternetAccountName Canonical Property</span></span>

  
  
<span data-ttu-id="7c84a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c84a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c84a-105">指定发送电子邮件的用户可见的电子邮件帐户名称。</span><span class="sxs-lookup"><span data-stu-id="7c84a-105">Specifies the user-visible email account name through which the email message is sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7c84a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7c84a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7c84a-107">dispidInetAcctName</span><span class="sxs-lookup"><span data-stu-id="7c84a-107">dispidInetAcctName</span></span>  <br/> |
|<span data-ttu-id="7c84a-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="7c84a-108">Property set:</span></span>  <br/> |<span data-ttu-id="7c84a-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="7c84a-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="7c84a-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="7c84a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7c84a-111">0x00008580</span><span class="sxs-lookup"><span data-stu-id="7c84a-111">0x00008580</span></span>  <br/> |
|<span data-ttu-id="7c84a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7c84a-112">Data type:</span></span>  <br/> |<span data-ttu-id="7c84a-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7c84a-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7c84a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7c84a-114">Area:</span></span>  <br/> |<span data-ttu-id="7c84a-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="7c84a-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7c84a-116">备注</span><span class="sxs-lookup"><span data-stu-id="7c84a-116">Remarks</span></span>

<span data-ttu-id="7c84a-117">此字符串的格式依赖于实现。</span><span class="sxs-lookup"><span data-stu-id="7c84a-117">The format of this string is implementation dependent.</span></span> <span data-ttu-id="7c84a-118">客户端可以使用此属性来确定邮件要发送到的服务器，但是可选的，并且该值对服务器没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="7c84a-118">This property can be used by the client to determine which server to direct the mail to, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7c84a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7c84a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7c84a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7c84a-120">Protocol specifications</span></span>

<span data-ttu-id="7c84a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c84a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7c84a-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="7c84a-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7c84a-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c84a-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7c84a-124">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7c84a-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7c84a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7c84a-125">Header files</span></span>

<span data-ttu-id="7c84a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7c84a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7c84a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7c84a-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7c84a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c84a-128">See also</span></span>



[<span data-ttu-id="7c84a-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7c84a-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7c84a-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7c84a-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7c84a-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7c84a-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7c84a-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7c84a-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

