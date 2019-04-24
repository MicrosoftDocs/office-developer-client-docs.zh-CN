---
title: PidTagProfileHomeServerFQDN 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 80273b50-bc16-4be2-8471-1a127b6786bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aef4a932da35f3c4955bc2f4b265b146775c6d87
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341592"
---
# <a name="pidtagprofilehomeserverfqdn-canonical-property"></a><span data-ttu-id="7593e-103">PidTagProfileHomeServerFQDN 规范属性</span><span class="sxs-lookup"><span data-stu-id="7593e-103">PidTagProfileHomeServerFQDN Canonical Property</span></span>

  
  
<span data-ttu-id="7593e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7593e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7593e-105">启用配置文件配置的 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="7593e-105">Enables Kerberos authentication of a profile configuration.</span></span>
  
****

|||
|:-----|:-----|
|<span data-ttu-id="7593e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7593e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7593e-107">PR_PROFILE_HOME_SERVER_FQDN</span><span class="sxs-lookup"><span data-stu-id="7593e-107">PR_PROFILE_HOME_SERVER_FQDN</span></span>  <br/> |
|<span data-ttu-id="7593e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7593e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7593e-109">0x662A001F</span><span class="sxs-lookup"><span data-stu-id="7593e-109">0x662A001F</span></span>  <br/> |
|<span data-ttu-id="7593e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7593e-110">Data type:</span></span>  <br/> |<span data-ttu-id="7593e-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7593e-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7593e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7593e-112">Area:</span></span>  <br/> |<span data-ttu-id="7593e-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="7593e-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7593e-114">注解</span><span class="sxs-lookup"><span data-stu-id="7593e-114">Remarks</span></span>

<span data-ttu-id="7593e-115">将此属性设置为用户的目录服务器的域名可直接连接到域控制器 (DC), 这对于配置为对 Microsoft Exchange server 2007 使用 Kerberos 身份验证的配置文件是必需的;早期版本, 通过在**PR_PROFILE_AUTH_PACKAGE**中设置**RPC_C_AUTHN_GSS_KERBEROS** 。</span><span class="sxs-lookup"><span data-stu-id="7593e-115">Setting this property to the Domain Name of the user's directory server allows direct connection to the Domain Controller (DC), which is necessary for a profile that has been configured to use Kerberos authentication against Microsoft Exchange Server 2007 and earlier versions, by setting **RPC_C_AUTHN_GSS_KERBEROS** in **PR_PROFILE_AUTH_PACKAGE**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7593e-116">Microsoft Exchange server 2010 和 Exchange server 2013 将对客户端访问服务器进行的通讯簿调用的处理与 Exchange Server 2007 和早期版本处理它们的方式不同。</span><span class="sxs-lookup"><span data-stu-id="7593e-116">Microsoft Exchange Server 2010 and Exchange Server 2013 handle address book calls made to the Client Access Server differently from the way in which Exchange Server 2007 and earlier versions handle them.</span></span> <span data-ttu-id="7593e-117">不会再使用 DSProxy 进程, 因此 Kerberos 身份验证可能会成功。</span><span class="sxs-lookup"><span data-stu-id="7593e-117">The DSProxy process is no longer used, so Kerberos authentication may succeed.</span></span> <span data-ttu-id="7593e-118">但是, 客户端仍将与 Exchange 服务器进行通信, 而不是直接与 DC 通信, 这可能不是您所需要的: 设置**PR_PROFILE_HOME_SERVER_FQDN**避免了这种情况。</span><span class="sxs-lookup"><span data-stu-id="7593e-118">However, the client would still be communicating with the Exchange server instead of directly with the DC, which may not be desired: Setting **PR_PROFILE_HOME_SERVER_FQDN** avoids this.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7593e-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7593e-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7593e-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7593e-120">Protocol specifications</span></span>

<span data-ttu-id="7593e-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7593e-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7593e-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7593e-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7593e-123">[[毫秒-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7593e-123">[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7593e-124">指定核心邮件存储对象的允许操作。</span><span class="sxs-lookup"><span data-stu-id="7593e-124">Specifies permissible operations for the core message store objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7593e-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7593e-125">Header files</span></span>

<span data-ttu-id="7593e-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7593e-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7593e-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7593e-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="7593e-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7593e-128">Mapitags.h</span></span>
  
> <span data-ttu-id="7593e-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7593e-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7593e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7593e-130">See also</span></span>



[<span data-ttu-id="7593e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7593e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7593e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7593e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7593e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7593e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7593e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7593e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

