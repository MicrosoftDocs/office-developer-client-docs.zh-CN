---
title: 网关可映射属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a51ee7e-d030-4f04-915b-ff8bd351207d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 07c215511f010741e69c08c184df0ca3ce461e13
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583615"
---
# <a name="gateway-mappable-properties"></a><span data-ttu-id="5f4b8-103">网关可映射属性</span><span class="sxs-lookup"><span data-stu-id="5f4b8-103">Gateway mappable properties</span></span>

<span data-ttu-id="5f4b8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f4b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f4b8-105">网关可映射属性是可能需要翻译时从一个消息域发送到其他的属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-105">Gateway-mappable properties are properties that may require translation when sent from one messaging domain to another.</span></span> <span data-ttu-id="5f4b8-106">MAPI 的网关可映射属性启用邮件，其中包含正确需要网关，以确保目标邮件系统使用它的信息。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-106">MAPI's gateway-mappable properties enable messages to include information that requires a gateway to ensure the destination messaging system uses it properly.</span></span> <span data-ttu-id="5f4b8-107">尽管无需网关开发人员提供此转换功能，但他们应考虑网关可映射属性作为有机会来提高处理的消息内容。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-107">Although gateway developers are not required to provide this translation capability, they should consider gateway-mappable properties as an opportunity to improve handling of message content.</span></span>
  
<span data-ttu-id="5f4b8-108">MAPI 指定五种类型的网关可映射的属性：</span><span class="sxs-lookup"><span data-stu-id="5f4b8-108">MAPI specifies five types of gateway-mappable properties:</span></span>
  
- <span data-ttu-id="5f4b8-109">显示名称</span><span class="sxs-lookup"><span data-stu-id="5f4b8-109">Display name</span></span>
    
- <span data-ttu-id="5f4b8-110">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="5f4b8-110">Email address</span></span>
    
- <span data-ttu-id="5f4b8-111">电子邮件类型</span><span class="sxs-lookup"><span data-stu-id="5f4b8-111">Email type</span></span>
    
- <span data-ttu-id="5f4b8-112">项标识符</span><span class="sxs-lookup"><span data-stu-id="5f4b8-112">Entry identifier</span></span>
    
- <span data-ttu-id="5f4b8-113">搜索关键字</span><span class="sxs-lookup"><span data-stu-id="5f4b8-113">Search key</span></span>
    
<span data-ttu-id="5f4b8-114">这是一套解决与收件人、 发件人、 报告收件人和委派发件人和收件人关联的属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-114">This is the set of addressing properties that are associated with recipients, senders, report recipients, and delegated senders and recipients.</span></span> <span data-ttu-id="5f4b8-115">为了帮助您定义这些属性，以便将网关专门处理它们的客户端，MAPI，请指定使用命名的属性和属性集的命名约定。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-115">To help your client define these properties so that a gateway handles them specially, MAPI specifies a naming convention using named properties and property sets.</span></span> <span data-ttu-id="5f4b8-116">五个属性集存在用于存放命名的属性，需要映射寻址属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-116">Five property sets exist to hold named properties, the addressing properties that require mapping.</span></span> <span data-ttu-id="5f4b8-117">没有为每种类型的可映射属性的一个属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-117">There is one property set for each type of mappable property.</span></span> <span data-ttu-id="5f4b8-118">将保留这些命名寻址属性的属性集如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-118">The property sets that will hold these named addressing properties are as follows.</span></span>
  
|<span data-ttu-id="5f4b8-119">**属性集**</span><span class="sxs-lookup"><span data-stu-id="5f4b8-119">**Property set**</span></span>|<span data-ttu-id="5f4b8-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f4b8-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f4b8-121">PS_ROUTING_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="5f4b8-121">PS_ROUTING_DISPLAY_NAME</span></span>  <br/> |<span data-ttu-id="5f4b8-122">包含用作显示名称的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-122">Contains string properties used as display names.</span></span>  <br/> |
|<span data-ttu-id="5f4b8-123">PS_ROUTING_EMAIL_ADDRESSES</span><span class="sxs-lookup"><span data-stu-id="5f4b8-123">PS_ROUTING_EMAIL_ADDRESSES</span></span>  <br/> |<span data-ttu-id="5f4b8-124">包含用作电子邮件地址的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-124">Contains string properties used as email addresses.</span></span>  <br/> |
|<span data-ttu-id="5f4b8-125">PS_ROUTING_ADDRTYPE</span><span class="sxs-lookup"><span data-stu-id="5f4b8-125">PS_ROUTING_ADDRTYPE</span></span>  <br/> |<span data-ttu-id="5f4b8-126">包含字符串属性用作电子邮件地址类型。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-126">Contains string properties used as email address types.</span></span>  <br/> |
|<span data-ttu-id="5f4b8-127">PS_ROUTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5f4b8-127">PS_ROUTING_ENTRYID</span></span>  <br/> |<span data-ttu-id="5f4b8-128">包含用作长期的项标识符的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-128">Contains binary properties used as long-term entry identifiers.</span></span>  <br/> |
|<span data-ttu-id="5f4b8-129">PS_ROUTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="5f4b8-129">PS_ROUTING_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="5f4b8-130">包含用作搜索关键字的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="5f4b8-130">Contains binary properties used as search keys.</span></span>  <br/> |
   

