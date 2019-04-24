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
ms.openlocfilehash: 6f1a399cac2adbae66dabf9383540bb089424d17
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320998"
---
# <a name="gateway-mappable-properties"></a><span data-ttu-id="20297-103">网关可映射属性</span><span class="sxs-lookup"><span data-stu-id="20297-103">Gateway mappable properties</span></span>

<span data-ttu-id="20297-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20297-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20297-105">网关可映射属性是指从一个邮件域发送到另一个邮件域时可能需要进行转换的属性。</span><span class="sxs-lookup"><span data-stu-id="20297-105">Gateway-mappable properties are properties that may require translation when sent from one messaging domain to another.</span></span> <span data-ttu-id="20297-106">MAPI 的网关-可映射属性使邮件能够包含需要网关的信息, 以确保目标邮件系统正常使用。</span><span class="sxs-lookup"><span data-stu-id="20297-106">MAPI's gateway-mappable properties enable messages to include information that requires a gateway to ensure the destination messaging system uses it properly.</span></span> <span data-ttu-id="20297-107">尽管不需要网关开发人员提供此转换功能, 但他们应考虑使用网关可映射属性作为改进邮件内容处理的机会。</span><span class="sxs-lookup"><span data-stu-id="20297-107">Although gateway developers are not required to provide this translation capability, they should consider gateway-mappable properties as an opportunity to improve handling of message content.</span></span>
  
<span data-ttu-id="20297-108">MAPI 指定了五种类型的网关-映射属性:</span><span class="sxs-lookup"><span data-stu-id="20297-108">MAPI specifies five types of gateway-mappable properties:</span></span>
  
- <span data-ttu-id="20297-109">可分辨名称 (DN)</span><span class="sxs-lookup"><span data-stu-id="20297-109">Display name</span></span>
    
- <span data-ttu-id="20297-110">显示名称</span><span class="sxs-lookup"><span data-stu-id="20297-110">Email address</span></span>
    
- <span data-ttu-id="20297-111">电子邮件类型</span><span class="sxs-lookup"><span data-stu-id="20297-111">Email type</span></span>
    
- <span data-ttu-id="20297-112">条目标识符</span><span class="sxs-lookup"><span data-stu-id="20297-112">Entry identifier</span></span>
    
- <span data-ttu-id="20297-113">搜索关键字</span><span class="sxs-lookup"><span data-stu-id="20297-113">Search key</span></span>
    
<span data-ttu-id="20297-114">这是与收件人、发件人、报告收件人以及委派的发件人和收件人相关联的一组地址属性。</span><span class="sxs-lookup"><span data-stu-id="20297-114">This is the set of addressing properties that are associated with recipients, senders, report recipients, and delegated senders and recipients.</span></span> <span data-ttu-id="20297-115">为了帮助您的客户端定义这些属性, 以便网关对它们进行专门处理, MAPI 使用命名属性和属性集指定命名约定。</span><span class="sxs-lookup"><span data-stu-id="20297-115">To help your client define these properties so that a gateway handles them specially, MAPI specifies a naming convention using named properties and property sets.</span></span> <span data-ttu-id="20297-116">有五个属性集可用于保留命名属性, 这是需要映射的寻址属性。</span><span class="sxs-lookup"><span data-stu-id="20297-116">Five property sets exist to hold named properties, the addressing properties that require mapping.</span></span> <span data-ttu-id="20297-117">为每种类型的类型映射属性设置了一个属性。</span><span class="sxs-lookup"><span data-stu-id="20297-117">There is one property set for each type of mappable property.</span></span> <span data-ttu-id="20297-118">将保留这些命名的寻址属性的属性集如下所示。</span><span class="sxs-lookup"><span data-stu-id="20297-118">The property sets that will hold these named addressing properties are as follows.</span></span>
  
|<span data-ttu-id="20297-119">**属性集**</span><span class="sxs-lookup"><span data-stu-id="20297-119">**Property set**</span></span>|<span data-ttu-id="20297-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="20297-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20297-121">PS_ROUTING_DISPLAY_NAME</span><span class="sxs-lookup"><span data-stu-id="20297-121">PS_ROUTING_DISPLAY_NAME</span></span>  <br/> |<span data-ttu-id="20297-122">包含用作显示名称的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="20297-122">Contains string properties used as display names.</span></span>  <br/> |
|<span data-ttu-id="20297-123">PS_ROUTING_EMAIL_ADDRESSES</span><span class="sxs-lookup"><span data-stu-id="20297-123">PS_ROUTING_EMAIL_ADDRESSES</span></span>  <br/> |<span data-ttu-id="20297-124">包含用作电子邮件地址的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="20297-124">Contains string properties used as email addresses.</span></span>  <br/> |
|<span data-ttu-id="20297-125">PS_ROUTING_ADDRTYPE</span><span class="sxs-lookup"><span data-stu-id="20297-125">PS_ROUTING_ADDRTYPE</span></span>  <br/> |<span data-ttu-id="20297-126">包含用作电子邮件地址类型的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="20297-126">Contains string properties used as email address types.</span></span>  <br/> |
|<span data-ttu-id="20297-127">PS_ROUTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="20297-127">PS_ROUTING_ENTRYID</span></span>  <br/> |<span data-ttu-id="20297-128">包含用作长期条目标识符的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="20297-128">Contains binary properties used as long-term entry identifiers.</span></span>  <br/> |
|<span data-ttu-id="20297-129">PS_ROUTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="20297-129">PS_ROUTING_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="20297-130">包含用作搜索键的二进制属性。</span><span class="sxs-lookup"><span data-stu-id="20297-130">Contains binary properties used as search keys.</span></span>  <br/> |
   

