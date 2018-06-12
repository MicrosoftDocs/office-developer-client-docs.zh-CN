---
title: PidTagProfileHomeServerFQDN 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 80273b50-bc16-4be2-8471-1a127b6786bb
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 398ff2fd4bab49c8279e198e3efa416c53abda7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778058"
---
# <a name="pidtagprofilehomeserverfqdn-canonical-property"></a><span data-ttu-id="14515-103">PidTagProfileHomeServerFQDN 规范属性</span><span class="sxs-lookup"><span data-stu-id="14515-103">PidTagProfileHomeServerFQDN Canonical Property</span></span>

  
  
<span data-ttu-id="14515-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="14515-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="14515-105">启用 Kerberos 身份验证的配置文件配置。</span><span class="sxs-lookup"><span data-stu-id="14515-105">Enables Kerberos authentication of a profile configuration.</span></span>
  
****

|||
|:-----|:-----|
|<span data-ttu-id="14515-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="14515-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="14515-107">PR_PROFILE_HOME_SERVER_FQDN</span><span class="sxs-lookup"><span data-stu-id="14515-107">PR_PROFILE_HOME_SERVER_FQDN</span></span>  <br/> |
|<span data-ttu-id="14515-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="14515-108">Identifier:</span></span>  <br/> |<span data-ttu-id="14515-109">0x662A001F</span><span class="sxs-lookup"><span data-stu-id="14515-109">0x662A001F</span></span>  <br/> |
|<span data-ttu-id="14515-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="14515-110">Data type:</span></span>  <br/> |<span data-ttu-id="14515-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="14515-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="14515-112">区域：</span><span class="sxs-lookup"><span data-stu-id="14515-112">Area:</span></span>  <br/> |<span data-ttu-id="14515-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="14515-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="14515-114">备注</span><span class="sxs-lookup"><span data-stu-id="14515-114">Remarks</span></span>

<span data-ttu-id="14515-115">此属性设置为用户的目录服务器的域名允许直接连接到域控制器 (DC)，它是已配置为使用针对 Microsoft Exchange Server 2007 的 Kerberos 身份验证的配置文件和早期版本中，通过在**PR_PROFILE_AUTH_PACKAGE**中设置**RPC_C_AUTHN_GSS_KERBEROS** 。</span><span class="sxs-lookup"><span data-stu-id="14515-115">Setting this property to the Domain Name of the user's directory server allows direct connection to the Domain Controller (DC), which is necessary for a profile that has been configured to use Kerberos authentication against Microsoft Exchange Server 2007 and earlier versions, by setting **RPC_C_AUTHN_GSS_KERBEROS** in **PR_PROFILE_AUTH_PACKAGE**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14515-116">Microsoft Exchange Server 2010 和 Exchange Server 2013 处理从 Exchange Server 2007 和早期版本进行处理的方式不同对客户端访问服务器的地址簿呼叫。</span><span class="sxs-lookup"><span data-stu-id="14515-116">Microsoft Exchange Server 2010 and Exchange Server 2013 handle address book calls made to the Client Access Server differently from the way in which Exchange Server 2007 and earlier versions handle them.</span></span> <span data-ttu-id="14515-117">不再使用 DSProxy 过程，因此 Kerberos 身份验证可能失败。</span><span class="sxs-lookup"><span data-stu-id="14515-117">The DSProxy process is no longer used, so Kerberos authentication may succeed.</span></span> <span data-ttu-id="14515-118">但是，客户端仍都将与 Exchange 服务器而不是直接与 DC，可能不需要通信： 设置**PR_PROFILE_HOME_SERVER_FQDN**避免这。</span><span class="sxs-lookup"><span data-stu-id="14515-118">However, the client would still be communicating with the Exchange server instead of directly with the DC, which may not be desired: Setting **PR_PROFILE_HOME_SERVER_FQDN** avoids this.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="14515-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="14515-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="14515-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="14515-120">Protocol specifications</span></span>

<span data-ttu-id="14515-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="14515-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="14515-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="14515-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="14515-123">[[MS OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="14515-123">[[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="14515-124">指定允许的操作的核心消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="14515-124">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="14515-125">头文件</span><span class="sxs-lookup"><span data-stu-id="14515-125">Header files</span></span>

<span data-ttu-id="14515-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="14515-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="14515-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="14515-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="14515-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="14515-128">Mapitags.h</span></span>
  
> <span data-ttu-id="14515-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="14515-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="14515-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14515-130">See also</span></span>



[<span data-ttu-id="14515-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="14515-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="14515-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="14515-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="14515-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="14515-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="14515-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="14515-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

