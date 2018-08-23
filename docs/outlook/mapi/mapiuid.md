---
title: MAPIUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIUID
api_type:
- COM
ms.assetid: 63eac3ee-e59b-4a06-8bb9-f72764d84bda
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f7ec60768ab07c56969f538f196a1f9df5dbed17
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587164"
---
# <a name="mapiuid"></a><span data-ttu-id="a228b-103">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="a228b-103">MAPIUID</span></span>

  
  
<span data-ttu-id="a228b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a228b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a228b-105">用于唯一标识服务提供商的[GUID](guid.md)结构字节顺序独立版本。</span><span class="sxs-lookup"><span data-stu-id="a228b-105">A byte-order independent version of a [GUID](guid.md) structure that is used to uniquely identify a service provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a228b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a228b-106">Header file:</span></span>  <br/> |<span data-ttu-id="a228b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a228b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="a228b-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="a228b-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="a228b-109">IsEqualMAPIUID</span><span class="sxs-lookup"><span data-stu-id="a228b-109">IsEqualMAPIUID</span></span>](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a><span data-ttu-id="a228b-110">Members</span><span class="sxs-lookup"><span data-stu-id="a228b-110">Members</span></span>

 <span data-ttu-id="a228b-111">**ab**</span><span class="sxs-lookup"><span data-stu-id="a228b-111">**ab**</span></span>
  
> <span data-ttu-id="a228b-112">包含一个 16 字节标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="a228b-112">An array that contains a 16-byte identifier.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a228b-113">注解</span><span class="sxs-lookup"><span data-stu-id="a228b-113">Remarks</span></span>

<span data-ttu-id="a228b-114">**MAPIUID**结构是置于 Intel® 处理器字节顺序的**GUID**结构。</span><span class="sxs-lookup"><span data-stu-id="a228b-114">A **MAPIUID** structure is a **GUID** structure put into Intel® processor byte order.</span></span> 
  
<span data-ttu-id="a228b-115">MAPI 以使它很少见这两个不同项具有相同标识符的一种创建**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="a228b-115">MAPI creates **MAPIUID** structures in a way that makes it very rare for two different items to have the same identifier.</span></span> <span data-ttu-id="a228b-116">可以存储**MAPIUID**结构中作为二进制属性或文件，而不考虑计算机存储或访问信息的字节排序。</span><span class="sxs-lookup"><span data-stu-id="a228b-116">**MAPIUID** structures can be stored as binary properties or as files, without regard to the byte ordering of the computer storing or accessing the information.</span></span> 
  
 <span data-ttu-id="a228b-117">使用**MAPIUID**结构：</span><span class="sxs-lookup"><span data-stu-id="a228b-117">**MAPIUID** structures are used:</span></span> 
  
- <span data-ttu-id="a228b-118">若要确定配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="a228b-118">To identify a profile section.</span></span>
    
- <span data-ttu-id="a228b-119">项标识符的消息中存储和通讯簿对象，用于标识负责服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a228b-119">In the entry identifiers of message store and address book objects to identify the responsible service provider.</span></span>
    
- <span data-ttu-id="a228b-120">在邮件的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a228b-120">In the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of messages.</span></span>
    
<span data-ttu-id="a228b-121">若要生成搜索关键字的**MAPIUID**标识符，服务提供商，请调用[IMAPISupport::NewUID](imapisupport-newuid.md)。</span><span class="sxs-lookup"><span data-stu-id="a228b-121">To generate a **MAPIUID** identifier for a search key, service providers call [IMAPISupport::NewUID](imapisupport-newuid.md).</span></span>
  
<span data-ttu-id="a228b-122">当客户端通过网络传输一条消息时，它应使用不会更改**MAPIUID**数据的字节顺序的协议或传输格式。</span><span class="sxs-lookup"><span data-stu-id="a228b-122">When a client transmits a message across a network, it should use a protocol or transmission format that does not change the byte order of **MAPIUID** data.</span></span> 
  
<span data-ttu-id="a228b-123">有关如何使用**MAPIUID**结构的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="a228b-123">For more information about how **MAPIUID** structures are used, see the following topics:</span></span> 
  
[<span data-ttu-id="a228b-124">注册服务提供程序唯一标识符</span><span class="sxs-lookup"><span data-stu-id="a228b-124">Registering Service Provider Unique Identifiers</span></span>](registering-service-provider-unique-identifiers.md)
  
[<span data-ttu-id="a228b-125">设置传输顺序</span><span class="sxs-lookup"><span data-stu-id="a228b-125">Setting Transport Order</span></span>](setting-transport-order.md)
  
## <a name="see-also"></a><span data-ttu-id="a228b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a228b-126">See also</span></span>



[<span data-ttu-id="a228b-127">GUID</span><span class="sxs-lookup"><span data-stu-id="a228b-127">GUID</span></span>](guid.md)
  
[<span data-ttu-id="a228b-128">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="a228b-128">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="a228b-129">IMAPISupport::NewUID</span><span class="sxs-lookup"><span data-stu-id="a228b-129">IMAPISupport::NewUID</span></span>](imapisupport-newuid.md)


[<span data-ttu-id="a228b-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a228b-130">MAPI Structures</span></span>](mapi-structures.md)

