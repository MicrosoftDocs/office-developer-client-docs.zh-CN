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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32269921"
---
# <a name="mapiuid"></a><span data-ttu-id="67643-103">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="67643-103">MAPIUID</span></span>

  
  
<span data-ttu-id="67643-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67643-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67643-105">用于唯一标识服务提供程序的[GUID](guid.md)结构的字节顺序独立版本。</span><span class="sxs-lookup"><span data-stu-id="67643-105">A byte-order independent version of a [GUID](guid.md) structure that is used to uniquely identify a service provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="67643-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="67643-106">Header file:</span></span>  <br/> |<span data-ttu-id="67643-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="67643-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="67643-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="67643-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="67643-109">IsEqualMAPIUID</span><span class="sxs-lookup"><span data-stu-id="67643-109">IsEqualMAPIUID</span></span>](isequalmapiuid.md) <br/> |
   
```cpp
typedef struct _MAPIUID
{
  BYTE ab[16];
} MAPIUID, FAR *LPMAPIUID;

```

## <a name="members"></a><span data-ttu-id="67643-110">Members</span><span class="sxs-lookup"><span data-stu-id="67643-110">Members</span></span>

 <span data-ttu-id="67643-111">**ab**</span><span class="sxs-lookup"><span data-stu-id="67643-111">**ab**</span></span>
  
> <span data-ttu-id="67643-112">包含16字节标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="67643-112">An array that contains a 16-byte identifier.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="67643-113">注解</span><span class="sxs-lookup"><span data-stu-id="67643-113">Remarks</span></span>

<span data-ttu-id="67643-114">**MAPIUID**结构是一个添加到英特尔®处理器字节顺序的**GUID**结构。</span><span class="sxs-lookup"><span data-stu-id="67643-114">A **MAPIUID** structure is a **GUID** structure put into Intel® processor byte order.</span></span> 
  
<span data-ttu-id="67643-115">MAPI 创建**MAPIUID**结构的方式非常少导致两个不同的项具有相同的标识符。</span><span class="sxs-lookup"><span data-stu-id="67643-115">MAPI creates **MAPIUID** structures in a way that makes it very rare for two different items to have the same identifier.</span></span> <span data-ttu-id="67643-116">**MAPIUID**结构可以存储为二进制属性或文件, 而无需考虑存储或访问信息的计算机的字节排序。</span><span class="sxs-lookup"><span data-stu-id="67643-116">**MAPIUID** structures can be stored as binary properties or as files, without regard to the byte ordering of the computer storing or accessing the information.</span></span> 
  
 <span data-ttu-id="67643-117">使用**MAPIUID**结构:</span><span class="sxs-lookup"><span data-stu-id="67643-117">**MAPIUID** structures are used:</span></span> 
  
- <span data-ttu-id="67643-118">标识配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="67643-118">To identify a profile section.</span></span>
    
- <span data-ttu-id="67643-119">在邮件存储区和通讯簿对象的条目标识符中, 用于标识负责的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="67643-119">In the entry identifiers of message store and address book objects to identify the responsible service provider.</span></span>
    
- <span data-ttu-id="67643-120">在邮件的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="67643-120">In the **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property of messages.</span></span>
    
<span data-ttu-id="67643-121">若要生成搜索密钥的**MAPIUID**标识符, 服务提供程序调用[IMAPISupport:: NewUID](imapisupport-newuid.md)。</span><span class="sxs-lookup"><span data-stu-id="67643-121">To generate a **MAPIUID** identifier for a search key, service providers call [IMAPISupport::NewUID](imapisupport-newuid.md).</span></span>
  
<span data-ttu-id="67643-122">当客户端通过网络传输邮件时, 它应使用不会更改**MAPIUID**数据字节顺序的协议或传输格式。</span><span class="sxs-lookup"><span data-stu-id="67643-122">When a client transmits a message across a network, it should use a protocol or transmission format that does not change the byte order of **MAPIUID** data.</span></span> 
  
<span data-ttu-id="67643-123">有关如何使用**MAPIUID**结构的详细信息, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="67643-123">For more information about how **MAPIUID** structures are used, see the following topics:</span></span> 
  
[<span data-ttu-id="67643-124">注册服务提供程序唯一标识符</span><span class="sxs-lookup"><span data-stu-id="67643-124">Registering Service Provider Unique Identifiers</span></span>](registering-service-provider-unique-identifiers.md)
  
[<span data-ttu-id="67643-125">设置传输顺序</span><span class="sxs-lookup"><span data-stu-id="67643-125">Setting Transport Order</span></span>](setting-transport-order.md)
  
## <a name="see-also"></a><span data-ttu-id="67643-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67643-126">See also</span></span>



[<span data-ttu-id="67643-127">GUID</span><span class="sxs-lookup"><span data-stu-id="67643-127">GUID</span></span>](guid.md)
  
[<span data-ttu-id="67643-128">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="67643-128">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="67643-129">IMAPISupport::NewUID</span><span class="sxs-lookup"><span data-stu-id="67643-129">IMAPISupport::NewUID</span></span>](imapisupport-newuid.md)


[<span data-ttu-id="67643-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="67643-130">MAPI Structures</span></span>](mapi-structures.md)

