---
title: PidTagProfileServerVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5d41a536-81ff-733c-2fd7-460798e057c8
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 571ac25d6bc738f8289e3019c342820682d08c28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778062"
---
# <a name="pidtagprofileserverversion-canonical-property"></a><span data-ttu-id="20cb3-103">PidTagProfileServerVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="20cb3-103">PidTagProfileServerVersion Canonical Property</span></span>

  
  
<span data-ttu-id="20cb3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="20cb3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="20cb3-105">指定的 Microsoft Outlook 配置文件中的帐户连接到 Microsoft Exchange Server 版本信息。</span><span class="sxs-lookup"><span data-stu-id="20cb3-105">Specifies information about the version of Microsoft Exchange Server to which accounts in a Microsoft Outlook profile are connected.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="20cb3-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="20cb3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="20cb3-107">PR_PROFILE_SERVER_VERSION</span><span class="sxs-lookup"><span data-stu-id="20cb3-107">PR_PROFILE_SERVER_VERSION</span></span>  <br/> |
|<span data-ttu-id="20cb3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="20cb3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="20cb3-109">0x661B</span><span class="sxs-lookup"><span data-stu-id="20cb3-109">0x661B</span></span>  <br/> |
|<span data-ttu-id="20cb3-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="20cb3-110">Property type:</span></span>  <br/> |<span data-ttu-id="20cb3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="20cb3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="20cb3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="20cb3-112">Area:</span></span>  <br/> |<span data-ttu-id="20cb3-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="20cb3-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="20cb3-114">备注</span><span class="sxs-lookup"><span data-stu-id="20cb3-114">Remarks</span></span>

<span data-ttu-id="20cb3-115">一个配置文件可以指定一个或多个帐户连接到 Exchange 服务器，但他们必须连接到同一 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="20cb3-115">A profile can specify one or more accounts that connect to an Exchange Server, but they must be connected to the same Exchange Server.</span></span>
  
<span data-ttu-id="20cb3-116">早于 Microsoft Office Outlook 2007 的 Outlook 版本可以写入此属性存储的活动配置文件连接到 Exchange Server 版本信息。</span><span class="sxs-lookup"><span data-stu-id="20cb3-116">Versions of Outlook earlier than Microsoft Office Outlook 2007 can write to this property to store information about the version of Exchange Server to which the active profile is connected.</span></span> <span data-ttu-id="20cb3-117">但是，版本信息的格式不同的不同版本的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="20cb3-117">However, the format of the version information varies for different versions of Exchange Server.</span></span> <span data-ttu-id="20cb3-118">例如， **PR_PROFILE_SERVER_VERSION** 6944 的十进制值表示仅主要中的 Outlook 存储区中的版本标识符的版本号**6.5.6944.3** Microsoft Exchange Server 2003。</span><span class="sxs-lookup"><span data-stu-id="20cb3-118">For example, Outlook stores in **PR_PROFILE_SERVER_VERSION** the decimal value 6944 to represent only the major build number in the version identifier of **6.5.6944.3** for Microsoft Exchange Server 2003.</span></span> <span data-ttu-id="20cb3-119">对于 Exchange 2007 连接，Outlook 存储的主版本号和主版本号的串联十六进制表示的属性中的这些号码。</span><span class="sxs-lookup"><span data-stu-id="20cb3-119">For an Exchange 2007 connection, Outlook stores the major version number and the major build number in a concatenated hexadecimal representation of these numbers in the property.</span></span> <span data-ttu-id="20cb3-120">Exchange 2007 版本的**8.0.685.24**标识符具有十进制主版本号 8 和主要版本号 685。</span><span class="sxs-lookup"><span data-stu-id="20cb3-120">An Exchange 2007 version identifier of **8.0.685.24** has a major version number 8 and a major build number 685 in decimal.</span></span> <span data-ttu-id="20cb3-121">您将这两个数字转换为十六进制数，获取 0x8 和 0x2AD。</span><span class="sxs-lookup"><span data-stu-id="20cb3-121">Converting both numbers to hexadecimal, you get 0x8 and 0x2AD.</span></span> <span data-ttu-id="20cb3-122">将这两个数字，Outlook 将值存储 0x82AD **PR_PROFILE_SERVER_VERSION**十六进制表示中。</span><span class="sxs-lookup"><span data-stu-id="20cb3-122">Concatenating these two numbers, Outlook stores the value 0x82AD in **PR_PROFILE_SERVER_VERSION** in hexadecimal representation.</span></span> 
  
<span data-ttu-id="20cb3-123">Outlook 2007 不读取或写入到此属性。</span><span class="sxs-lookup"><span data-stu-id="20cb3-123">Outlook 2007 does not read or write to this property.</span></span> <span data-ttu-id="20cb3-124">它支持**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**。</span><span class="sxs-lookup"><span data-stu-id="20cb3-124">It supports **[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**.</span></span> 
  
<span data-ttu-id="20cb3-125">只有一个**PR_PROFILE_SERVER_VERSION**或**PR_PROFILE_SERVER_FULL_VERSION**可能存在于配置文件，但以下任意始终存在配置文件中不能保证。</span><span class="sxs-lookup"><span data-stu-id="20cb3-125">Only one of **PR_PROFILE_SERVER_VERSION** or **PR_PROFILE_SERVER_FULL_VERSION** is likely to exist in a profile, but there is no guarantee that either always exists in a profile.</span></span> <span data-ttu-id="20cb3-126">Outlook 不会写入这两个属性，直到成功连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="20cb3-126">Outlook does not write to either property until it has successfully connected to the Exchange Server.</span></span> 
  
<span data-ttu-id="20cb3-127">在 Outlook 对象模型中，您可以使用**NameSpace**对象的**ExchangeMailboxServerVersion**属性查找在其托管主动邮箱的 Exchange Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="20cb3-127">In the Outlook object model, you can use the **ExchangeMailboxServerVersion** property of the **NameSpace** object to find the version of Exchange Server on which the active mailbox is hosted.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="20cb3-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="20cb3-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="20cb3-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="20cb3-129">Protocol specifications</span></span>

<span data-ttu-id="20cb3-130">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="20cb3-130">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="20cb3-131">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="20cb3-131">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="20cb3-132">头文件</span><span class="sxs-lookup"><span data-stu-id="20cb3-132">Header files</span></span>

<span data-ttu-id="20cb3-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="20cb3-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="20cb3-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="20cb3-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="20cb3-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="20cb3-135">Mapitags.h</span></span>
  
> <span data-ttu-id="20cb3-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="20cb3-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="20cb3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20cb3-137">See also</span></span>



[<span data-ttu-id="20cb3-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="20cb3-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="20cb3-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="20cb3-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="20cb3-140">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="20cb3-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="20cb3-141">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="20cb3-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

