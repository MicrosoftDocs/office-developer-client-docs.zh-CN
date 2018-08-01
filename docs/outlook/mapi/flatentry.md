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
ms.openlocfilehash: 2f5f4d50b085c437d1caab5f70dcb741afe090bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774938"
---
# <a name="flatentry"></a><span data-ttu-id="96135-103">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="96135-103">FLATENTRY</span></span>

  
  
<span data-ttu-id="96135-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96135-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96135-105">[ENTRYID](entryid.md)结构加上指定**ENTRYID**结构大小的字节数。</span><span class="sxs-lookup"><span data-stu-id="96135-105">An [ENTRYID](entryid.md) structure plus a byte count that specifies the size of the **ENTRYID** structure.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="96135-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="96135-106">Header file:</span></span>  <br/> |<span data-ttu-id="96135-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="96135-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="96135-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="96135-108">Related macros:</span></span>  <br/> |<span data-ttu-id="96135-109">[cbFLATENTRY](cbflatentry.md) [CbNewFLATENTRY](cbnewflatentry.md)</span><span class="sxs-lookup"><span data-stu-id="96135-109">[cbFLATENTRY](cbflatentry.md), [CbNewFLATENTRY](cbnewflatentry.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE abEntry[MAPI_DIM];
} FLATENTRY, FAR *LPFLATENTRY;

```

## <a name="members"></a><span data-ttu-id="96135-110">Members</span><span class="sxs-lookup"><span data-stu-id="96135-110">Members</span></span>

 <span data-ttu-id="96135-111">**cb**</span><span class="sxs-lookup"><span data-stu-id="96135-111">**cb**</span></span>
  
> <span data-ttu-id="96135-112">**AbEntry**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="96135-112">Count of bytes in the **abEntry** member.</span></span> 
    
 <span data-ttu-id="96135-113">**abEntry**</span><span class="sxs-lookup"><span data-stu-id="96135-113">**abEntry**</span></span>
  
> <span data-ttu-id="96135-114">包含数组标志和二进制数据的完整输入标识符。</span><span class="sxs-lookup"><span data-stu-id="96135-114">The complete entry identifier that includes the array of flags and binary data.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="96135-115">说明</span><span class="sxs-lookup"><span data-stu-id="96135-115">Remarks</span></span>

<span data-ttu-id="96135-116">**FLATENTRY**结构类似于[ENTRYID](entryid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="96135-116">A **FLATENTRY** structure resembles an [ENTRYID](entryid.md) structure.</span></span> <span data-ttu-id="96135-117">但是，有一些区别：</span><span class="sxs-lookup"><span data-stu-id="96135-117">However, there are some differences:</span></span> 
  
- <span data-ttu-id="96135-118">**FLATENTRY**结构存储的项标识符; 的大小未为**ENTRYID** 。</span><span class="sxs-lookup"><span data-stu-id="96135-118">A **FLATENTRY** structure stores the size of the entry identifier; **ENTRYID** does not.</span></span> 
    
- <span data-ttu-id="96135-119">**FLATENTRY**结构将一起条目标识符; 的其余部分标志数据存储**ENTRYID**单独存储这些。</span><span class="sxs-lookup"><span data-stu-id="96135-119">A **FLATENTRY** structure stores the flag data together with the rest of the entry identifier; **ENTRYID** stores them separately.</span></span> 
    
- <span data-ttu-id="96135-120">**FLATENTRY**结构用于存储在文件中的项标识符或而[IMAPIProp](imapipropiunknown.md)接口方法和以下**OpenEntry**方法使用**ENTRYID**结构中的字节流传递： [IABLogon:: OpenEntry](iablogon-openentry.md)， [IAddrBook::OpenEntry](iaddrbook-openentry.md)、 [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)、 [IMAPISession::OpenEntry](imapisession-openentry.md)、 [IMAPISupport::OpenEntry](imapisupport-openentry.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)、 [IMSLogon::OpenEntry](imslogon-openentry.md)</span><span class="sxs-lookup"><span data-stu-id="96135-120">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes whereas an **ENTRYID** structure is used by the [IMAPIProp](imapipropiunknown.md) interface methods and by the following **OpenEntry** methods: [IABLogon::OpenEntry](iablogon-openentry.md), [IAddrBook::OpenEntry](iaddrbook-openentry.md), [IMAPIContainer::OpenEntry](imapicontainer-openentry.md), [IMAPISession::OpenEntry](imapisession-openentry.md), [IMAPISupport::OpenEntry](imapisupport-openentry.md), [IMsgStore::OpenEntry](imsgstore-openentry.md), [IMSLogon::OpenEntry](imslogon-openentry.md)</span></span>
    
- <span data-ttu-id="96135-121">**FLATENTRY**结构用于存储在文件中的项标识符，或将其传递中的字节流。</span><span class="sxs-lookup"><span data-stu-id="96135-121">A **FLATENTRY** structure is used to store an entry identifier in a file or pass it in a stream of bytes.</span></span> <span data-ttu-id="96135-122">**ENTRYID**结构用于存储在磁盘上的项标识符。</span><span class="sxs-lookup"><span data-stu-id="96135-122">An **ENTRYID** structure is used to store an entry identifier on disk.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="96135-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96135-123">See also</span></span>



[<span data-ttu-id="96135-124">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="96135-124">ENTRYID</span></span>](entryid.md)


[<span data-ttu-id="96135-125">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="96135-125">MAPI Structures</span></span>](mapi-structures.md)

