---
title: FLATENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATENTRY
api_type:
- COM
ms.assetid: 03e53e08-9113-4101-84c9-ccf6d43127f6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e47f4e0d1ab9ab3ecfd53932b8ef26440134c603
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407240"
---
# <a name="flatentry"></a><span data-ttu-id="76261-103">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="76261-103">FLATENTRY</span></span>

  
  
<span data-ttu-id="76261-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="76261-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="76261-105">[ENTRYID](entryid.md)结构加上指定 **ENTRYID** 结构大小的字节计数。</span><span class="sxs-lookup"><span data-stu-id="76261-105">An [ENTRYID](entryid.md) structure plus a byte count that specifies the size of the **ENTRYID** structure.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76261-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="76261-106">Header file:</span></span>  <br/> |<span data-ttu-id="76261-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="76261-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="76261-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="76261-108">Related macros:</span></span>  <br/> |<span data-ttu-id="76261-109">[cbFLATENTRY](cbflatentry.md) [、CbNewFLATENTRY](cbnewflatentry.md)</span><span class="sxs-lookup"><span data-stu-id="76261-109">[cbFLATENTRY](cbflatentry.md), [CbNewFLATENTRY](cbnewflatentry.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} FLATENTRY, FAR *LPFLATENTRY;

```

## <a name="members"></a><span data-ttu-id="76261-110">Members</span><span class="sxs-lookup"><span data-stu-id="76261-110">Members</span></span>

 <span data-ttu-id="76261-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="76261-111">**cb**</span></span>
  
> <span data-ttu-id="76261-112">**abEntry** 成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="76261-112">Count of bytes in the **abEntry** member.</span></span> 
    
 <span data-ttu-id="76261-113">**abEntry**</span><span class="sxs-lookup"><span data-stu-id="76261-113">**abEntry**</span></span>
  
> <span data-ttu-id="76261-114">包含标志和二进制数据数组的完整条目标识符。</span><span class="sxs-lookup"><span data-stu-id="76261-114">The complete entry identifier that includes the array of flags and binary data.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="76261-115">备注</span><span class="sxs-lookup"><span data-stu-id="76261-115">Remarks</span></span>

<span data-ttu-id="76261-116">**FLATENTRY** 结构类似于 [ENTRYID](entryid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="76261-116">A **FLATENTRY** structure resembles an [ENTRYID](entryid.md) structure.</span></span> <span data-ttu-id="76261-117">但是，存在一些差异：</span><span class="sxs-lookup"><span data-stu-id="76261-117">However, there are some differences:</span></span> 
  
- <span data-ttu-id="76261-118">**FLATENTRY** 结构存储条目标识符的大小;**ENTRYID** 不会。</span><span class="sxs-lookup"><span data-stu-id="76261-118">A **FLATENTRY** structure stores the size of the entry identifier; **ENTRYID** does not.</span></span> 
    
- <span data-ttu-id="76261-119">**FLATENTRY** 结构将标志数据与条目标识符的其余部分一起存储;**ENTRYID** 单独存储它们。</span><span class="sxs-lookup"><span data-stu-id="76261-119">A **FLATENTRY** structure stores the flag data together with the rest of the entry identifier; **ENTRYID** stores them separately.</span></span> 
    
- <span data-ttu-id="76261-120">**FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中，**而 ENTRYID** 结构由 [IMAPIProp](imapipropiunknown.md)接口方法和以下 **OpenEntry** 方法使用 [：IABLogon：：OpenEntry](iablogon-openentry.md)和 [IAddrBook ：：OpenEntry](iaddrbook-openentry.md)、 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md)、 [IMAPISession：：OpenEntry](imapisession-openentry.md)、 [IMAPISupport：：OpenEntry](imapisupport-openentry.md)、 [IMsgStore：：OpenEntry](imsgstore-openentry.md)、 [IMSLogon：：OpenEntry](imslogon-openentry.md)</span><span class="sxs-lookup"><span data-stu-id="76261-120">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes whereas an **ENTRYID** structure is used by the [IMAPIProp](imapipropiunknown.md) interface methods and by the following **OpenEntry** methods: [IABLogon::OpenEntry](iablogon-openentry.md), [IAddrBook::OpenEntry](iaddrbook-openentry.md), [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), [IMAPISupport::OpenEntry](imapisupport-openentry.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), [IMSLogon::OpenEntry](imslogon-openentry.md)</span></span>
    
- <span data-ttu-id="76261-121">**FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中。</span><span class="sxs-lookup"><span data-stu-id="76261-121">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes.</span></span> <span data-ttu-id="76261-122">**ENTRYID** 结构用于在磁盘上存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="76261-122">An **ENTRYID** structure is used to store an entry identifier on disk.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="76261-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76261-123">See also</span></span>



[<span data-ttu-id="76261-124">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="76261-124">ENTRYID</span></span>](entryid.md)


[<span data-ttu-id="76261-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="76261-125">MAPI Structures</span></span>](mapi-structures.md)

