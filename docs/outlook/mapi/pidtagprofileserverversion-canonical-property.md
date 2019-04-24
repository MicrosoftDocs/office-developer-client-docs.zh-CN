---
title: PidTagProfileServerVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5d41a536-81ff-733c-2fd7-460798e057c8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 84ff229e9914ec9074d61023873279b110fb606a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286564"
---
# <a name="pidtagprofileserverversion-canonical-property"></a><span data-ttu-id="09641-103">PidTagProfileServerVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="09641-103">PidTagProfileServerVersion Canonical Property</span></span>

  
  
<span data-ttu-id="09641-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="09641-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="09641-105">指定与 microsoft Outlook 配置文件中的帐户连接的 microsoft Exchange Server 版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="09641-105">Specifies information about the version of Microsoft Exchange Server to which accounts in a Microsoft Outlook profile are connected.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="09641-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="09641-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="09641-107">PR_PROFILE_SERVER_VERSION</span><span class="sxs-lookup"><span data-stu-id="09641-107">PR_PROFILE_SERVER_VERSION</span></span>  <br/> |
|<span data-ttu-id="09641-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="09641-108">Identifier:</span></span>  <br/> |<span data-ttu-id="09641-109">0x661B</span><span class="sxs-lookup"><span data-stu-id="09641-109">0x661B</span></span>  <br/> |
|<span data-ttu-id="09641-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="09641-110">Property type:</span></span>  <br/> |<span data-ttu-id="09641-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="09641-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="09641-112">区域：</span><span class="sxs-lookup"><span data-stu-id="09641-112">Area:</span></span>  <br/> |<span data-ttu-id="09641-113">MAPI 配置文件配置</span><span class="sxs-lookup"><span data-stu-id="09641-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="09641-114">注解</span><span class="sxs-lookup"><span data-stu-id="09641-114">Remarks</span></span>

<span data-ttu-id="09641-115">配置文件可以指定连接到 exchange 服务器的一个或多个帐户, 但这些帐户必须连接到同一个 exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="09641-115">A profile can specify one or more accounts that connect to an Exchange Server, but they must be connected to the same Exchange Server.</span></span>
  
<span data-ttu-id="09641-116">早于 Microsoft Office outlook 2007 的 outlook 版本可以写入此属性, 以存储与活动配置文件连接的 Exchange 服务器版本相关信息。</span><span class="sxs-lookup"><span data-stu-id="09641-116">Versions of Outlook earlier than Microsoft Office Outlook 2007 can write to this property to store information about the version of Exchange Server to which the active profile is connected.</span></span> <span data-ttu-id="09641-117">但是, 版本信息的格式因不同版本的 Exchange Server 而异。</span><span class="sxs-lookup"><span data-stu-id="09641-117">However, the format of the version information varies for different versions of Exchange Server.</span></span> <span data-ttu-id="09641-118">例如, Outlook 在**PR_PROFILE_SERVER_VERSION**中存储十进制值 6944, 以仅表示 Microsoft Exchange SERVER 2003 的**6.5.6944.3**版本标识符中的主要内部版本号。</span><span class="sxs-lookup"><span data-stu-id="09641-118">For example, Outlook stores in **PR_PROFILE_SERVER_VERSION** the decimal value 6944 to represent only the major build number in the version identifier of **6.5.6944.3** for Microsoft Exchange Server 2003.</span></span> <span data-ttu-id="09641-119">对于 Exchange 2007 连接, Outlook 将主版本号和主要内部版本号存储在属性中这些数字的连接的十六进制表示形式中。</span><span class="sxs-lookup"><span data-stu-id="09641-119">For an Exchange 2007 connection, Outlook stores the major version number and the major build number in a concatenated hexadecimal representation of these numbers in the property.</span></span> <span data-ttu-id="09641-120">**8.0.685.24**的 Exchange 2007 版本标识符的主要版本号为 8, 主要版本号为685的十进制数。</span><span class="sxs-lookup"><span data-stu-id="09641-120">An Exchange 2007 version identifier of **8.0.685.24** has a major version number 8 and a major build number 685 in decimal.</span></span> <span data-ttu-id="09641-121">将这两个数字都转换为十六进制, 可以获取0x8 和0x2AD。</span><span class="sxs-lookup"><span data-stu-id="09641-121">Converting both numbers to hexadecimal, you get 0x8 and 0x2AD.</span></span> <span data-ttu-id="09641-122">Outlook 将这两个数字串联在**PR_PROFILE_SERVER_VERSION**中以十六进制表示形式存储值0x82AD。</span><span class="sxs-lookup"><span data-stu-id="09641-122">Concatenating these two numbers, Outlook stores the value 0x82AD in **PR_PROFILE_SERVER_VERSION** in hexadecimal representation.</span></span> 
  
<span data-ttu-id="09641-123">Outlook 2007 不会读取或写入该属性。</span><span class="sxs-lookup"><span data-stu-id="09641-123">Outlook 2007 does not read or write to this property.</span></span> <span data-ttu-id="09641-124">它支持**[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**。</span><span class="sxs-lookup"><span data-stu-id="09641-124">It supports **[PR_PROFILE_SERVER_FULL_VERSION](pidtagprofileserverfullversion-canonical-property.md)**.</span></span> 
  
<span data-ttu-id="09641-125">只有**PR_PROFILE_SERVER_VERSION**或 PR_PROFILE_SERVER_FULL_VERSION 中的一个可能存在于配置文件中, 但不能保证在配置文件中始终存在这两个\*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="09641-125">Only one of **PR_PROFILE_SERVER_VERSION** or **PR_PROFILE_SERVER_FULL_VERSION** is likely to exist in a profile, but there is no guarantee that either always exists in a profile.</span></span> <span data-ttu-id="09641-126">Outlook 在成功连接到 Exchange 服务器之前, 不会写入其中的任何一个属性。</span><span class="sxs-lookup"><span data-stu-id="09641-126">Outlook does not write to either property until it has successfully connected to the Exchange Server.</span></span> 
  
<span data-ttu-id="09641-127">在 Outlook 对象模型中, 可以使用**NameSpace**对象的**ExchangeMailboxServerVersion**属性来查找托管活动邮箱的 Exchange 服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="09641-127">In the Outlook object model, you can use the **ExchangeMailboxServerVersion** property of the **NameSpace** object to find the version of Exchange Server on which the active mailbox is hosted.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="09641-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="09641-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="09641-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="09641-129">Protocol specifications</span></span>

<span data-ttu-id="09641-130">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="09641-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="09641-131">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="09641-131">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="09641-132">头文件</span><span class="sxs-lookup"><span data-stu-id="09641-132">Header files</span></span>

<span data-ttu-id="09641-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="09641-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="09641-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="09641-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="09641-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="09641-135">Mapitags.h</span></span>
  
> <span data-ttu-id="09641-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="09641-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="09641-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09641-137">See also</span></span>



[<span data-ttu-id="09641-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="09641-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="09641-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="09641-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="09641-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="09641-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="09641-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="09641-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

