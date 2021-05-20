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
ms.openlocfilehash: da314205f7d2dd746b72aa7e2b5ff2a13bb0c21b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432203"
---
# <a name="mapiuid"></a><span data-ttu-id="05da2-103">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="05da2-103">MAPIUID</span></span>

  
  
<span data-ttu-id="05da2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="05da2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="05da2-105">GUID 结构的独立字节顺序版本，[](guid.md)用于唯一标识服务提供商。</span><span class="sxs-lookup"><span data-stu-id="05da2-105">A byte-order independent version of a [GUID](guid.md) structure that is used to uniquely identify a service provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="05da2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="05da2-106">Header file:</span></span>  <br/> |<span data-ttu-id="05da2-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="05da2-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="05da2-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="05da2-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="05da2-109">IsEqualMAPIUID</span><span class="sxs-lookup"><span data-stu-id="05da2-109">IsEqualMAPIUID</span></span>](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a><span data-ttu-id="05da2-110">Members</span><span class="sxs-lookup"><span data-stu-id="05da2-110">Members</span></span>

 <span data-ttu-id="05da2-111">**ab**</span><span class="sxs-lookup"><span data-stu-id="05da2-111">**ab**</span></span>
  
> <span data-ttu-id="05da2-112">包含 16 字节标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="05da2-112">An array that contains a 16-byte identifier.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="05da2-113">备注</span><span class="sxs-lookup"><span data-stu-id="05da2-113">Remarks</span></span>

<span data-ttu-id="05da2-114">**MAPIUID** 结构是一种 **GUID** 结构，®处理器字节顺序。</span><span class="sxs-lookup"><span data-stu-id="05da2-114">A **MAPIUID** structure is a **GUID** structure put into Intel® processor byte order.</span></span> 
  
<span data-ttu-id="05da2-115">MAPI 创建 **MAPIUID** 结构的方式使得两个不同的项具有相同的标识符非常少见。</span><span class="sxs-lookup"><span data-stu-id="05da2-115">MAPI creates **MAPIUID** structures in a way that makes it very rare for two different items to have the same identifier.</span></span> <span data-ttu-id="05da2-116">**MAPIUID** 结构可以存储为二进制属性或文件，而不考虑计算机存储或访问信息的字节顺序。</span><span class="sxs-lookup"><span data-stu-id="05da2-116">**MAPIUID** structures can be stored as binary properties or as files, without regard to the byte ordering of the computer storing or accessing the information.</span></span> 
  
 <span data-ttu-id="05da2-117">**使用 MAPIUID** 结构：</span><span class="sxs-lookup"><span data-stu-id="05da2-117">**MAPIUID** structures are used:</span></span> 
  
- <span data-ttu-id="05da2-118">标识配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="05da2-118">To identify a profile section.</span></span>
    
- <span data-ttu-id="05da2-119">在邮件存储和通讯簿对象的条目标识符中，以标识负责的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="05da2-119">In the entry identifiers of message store and address book objects to identify the responsible service provider.</span></span>
    
- <span data-ttu-id="05da2-120">In the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of messages.</span><span class="sxs-lookup"><span data-stu-id="05da2-120">In the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of messages.</span></span>
    
<span data-ttu-id="05da2-121">若要为搜索密钥 **生成 MAPIUID** 标识符，服务提供商调用 [IMAPISupport：：NewUID](imapisupport-newuid.md)。</span><span class="sxs-lookup"><span data-stu-id="05da2-121">To generate a **MAPIUID** identifier for a search key, service providers call [IMAPISupport::NewUID](imapisupport-newuid.md).</span></span>
  
<span data-ttu-id="05da2-122">当客户端跨网络传输邮件时，它应当使用不更改 **MAPIUID** 数据的字节顺序的协议或传输格式。</span><span class="sxs-lookup"><span data-stu-id="05da2-122">When a client transmits a message across a network, it should use a protocol or transmission format that does not change the byte order of **MAPIUID** data.</span></span> 
  
<span data-ttu-id="05da2-123">有关如何使用 **MAPIUID** 结构的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="05da2-123">For more information about how **MAPIUID** structures are used, see the following topics:</span></span> 
  
[<span data-ttu-id="05da2-124">注册服务提供程序唯一标识符</span><span class="sxs-lookup"><span data-stu-id="05da2-124">Registering Service Provider Unique Identifiers</span></span>](registering-service-provider-unique-identifiers.md)
  
[<span data-ttu-id="05da2-125">设置传输顺序</span><span class="sxs-lookup"><span data-stu-id="05da2-125">Setting Transport Order</span></span>](setting-transport-order.md)
  
## <a name="see-also"></a><span data-ttu-id="05da2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05da2-126">See also</span></span>



[<span data-ttu-id="05da2-127">GUID</span><span class="sxs-lookup"><span data-stu-id="05da2-127">GUID</span></span>](guid.md)
  
[<span data-ttu-id="05da2-128">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="05da2-128">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="05da2-129">IMAPISupport::NewUID</span><span class="sxs-lookup"><span data-stu-id="05da2-129">IMAPISupport::NewUID</span></span>](imapisupport-newuid.md)


[<span data-ttu-id="05da2-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="05da2-130">MAPI Structures</span></span>](mapi-structures.md)

