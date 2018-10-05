---
title: IProxyStoreObjectUnwrapNoRef
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject.UnwrapNoRef
api_type:
- COM
ms.assetid: 1122b6e0-e7e1-e68a-e090-435777343d04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef9f506c1a95fec86c7f092b0299198e6149d3ba
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382930"
---
# <a name="iproxystoreobjectunwrapnoref"></a><span data-ttu-id="74075-103">IProxyStoreObject::UnwrapNoRef</span><span class="sxs-lookup"><span data-stu-id="74075-103">IProxyStoreObject::UnwrapNoRef</span></span>

  
  
<span data-ttu-id="74075-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74075-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74075-105">获取一个指向一个解包的 Internet 消息访问协议 (IMAP) 存储对象，提供对基础个人文件夹文件 (PST) 的访问而不调用同步和下载项目。</span><span class="sxs-lookup"><span data-stu-id="74075-105">Gets a pointer to an unwrapped Internet Message Access Protocol (IMAP) store object that provides access to the underlying Personal Folders file (PST) without invoking synchronization and downloading the items.</span></span>
  
```cpp
HRESULT IProxyStoreObject::UnwrapNoRef (     LPVOID *ppvObject ); 
```

## <a name="parameters"></a><span data-ttu-id="74075-106">参数</span><span class="sxs-lookup"><span data-stu-id="74075-106">Parameters</span></span>

 <span data-ttu-id="74075-107">_ppvObject_</span><span class="sxs-lookup"><span data-stu-id="74075-107">_ppvObject_</span></span>
  
> <span data-ttu-id="74075-108">[输出]指向[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)解包的存储对象。</span><span class="sxs-lookup"><span data-stu-id="74075-108">[out] Pointer to an [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) store object that is unwrapped.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="74075-109">返回值</span><span class="sxs-lookup"><span data-stu-id="74075-109">Return values</span></span>

<span data-ttu-id="74075-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74075-110">S_OK</span></span>
  
- <span data-ttu-id="74075-111">调用成功，并且已在_ppvObject_返回指向解包接口的指针。</span><span class="sxs-lookup"><span data-stu-id="74075-111">The call was successful and a pointer to an unwrapped interface has been returned in  _ppvObject_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="74075-112">说明</span><span class="sxs-lookup"><span data-stu-id="74075-112">Remarks</span></span>

<span data-ttu-id="74075-113">第一个过程 IMAP 存储区，没有访问存储区中的一条消息可以强制尝试下载整个邮件的同步。</span><span class="sxs-lookup"><span data-stu-id="74075-113">Without first unwrapping an IMAP store, accessing a message in the store can force a synchronization that attempts to download the entire message.</span></span> <span data-ttu-id="74075-114">使用解包的存储而不会触发下载允许访问当前状态的消息。</span><span class="sxs-lookup"><span data-stu-id="74075-114">Using the unwrapped store allows access to the message in its current state without triggering a download.</span></span>
  
<span data-ttu-id="74075-115">由于**UnwrapNoRef**不会增加到解包的存储对象，此新指针的引用计数成功调用**UnwrapNoRef**后，您应调用[IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)维护引用计数。</span><span class="sxs-lookup"><span data-stu-id="74075-115">Because **UnwrapNoRef** does not increment the reference count for this new pointer to the unwrapped store object, after successfully calling **UnwrapNoRef**, you should call [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) to maintain the reference count.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="74075-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74075-116">See also</span></span>



[<span data-ttu-id="74075-117">IProxyStoreObject</span><span class="sxs-lookup"><span data-stu-id="74075-117">IProxyStoreObject</span></span>](iproxystoreobject.md)

