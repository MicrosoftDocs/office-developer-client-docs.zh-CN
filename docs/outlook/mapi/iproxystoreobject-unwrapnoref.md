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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ef9f506c1a95fec86c7f092b0299198e6149d3ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320151"
---
# <a name="iproxystoreobjectunwrapnoref"></a><span data-ttu-id="55277-103">IProxyStoreObject::UnwrapNoRef</span><span class="sxs-lookup"><span data-stu-id="55277-103">IProxyStoreObject::UnwrapNoRef</span></span>

  
  
<span data-ttu-id="55277-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55277-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55277-105">获取一个指向未包装的 Internet 邮件访问协议 (IMAP) 存储对象的指针，该对象提供对基础个人文件夹文件 (PST) 的访问，而无需调用同步和下载项目。</span><span class="sxs-lookup"><span data-stu-id="55277-105">Gets a pointer to an unwrapped Internet Message Access Protocol (IMAP) store object that provides access to the underlying Personal Folders file (PST) without invoking synchronization and downloading the items.</span></span>
  
```cpp
HRESULT IProxyStoreObject::UnwrapNoRef (     LPVOID *ppvObject ); 
```

## <a name="parameters"></a><span data-ttu-id="55277-106">参数</span><span class="sxs-lookup"><span data-stu-id="55277-106">Parameters</span></span>

 <span data-ttu-id="55277-107">_ppvObject_</span><span class="sxs-lookup"><span data-stu-id="55277-107">_ppvObject_</span></span>
  
> <span data-ttu-id="55277-108">[out]指向未包 [的 IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 存储对象的指针。</span><span class="sxs-lookup"><span data-stu-id="55277-108">[out] Pointer to an [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) store object that is unwrapped.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="55277-109">返回值</span><span class="sxs-lookup"><span data-stu-id="55277-109">Return values</span></span>

<span data-ttu-id="55277-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="55277-110">S_OK</span></span>
  
- <span data-ttu-id="55277-111">调用成功  _，ppvObject_ 中返回了指向未包接口的指针。</span><span class="sxs-lookup"><span data-stu-id="55277-111">The call was successful and a pointer to an unwrapped interface has been returned in  _ppvObject_.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="55277-112">备注</span><span class="sxs-lookup"><span data-stu-id="55277-112">Remarks</span></span>

<span data-ttu-id="55277-113">如果不首先解包 IMAP 存储，访问存储中的邮件可能会强制同步尝试下载整个邮件。</span><span class="sxs-lookup"><span data-stu-id="55277-113">Without first unwrapping an IMAP store, accessing a message in the store can force a synchronization that attempts to download the entire message.</span></span> <span data-ttu-id="55277-114">使用未包装存储，可以在不触发下载的情况下，以当前状态访问邮件。</span><span class="sxs-lookup"><span data-stu-id="55277-114">Using the unwrapped store allows access to the message in its current state without triggering a download.</span></span>
  
<span data-ttu-id="55277-115">由于 **UnwrapNoRef** 不增加指向未包装存储对象的此新指针的引用计数，因此在成功调用 **UnwrapNoRef** 后，应调用 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) 以保持引用计数。</span><span class="sxs-lookup"><span data-stu-id="55277-115">Because **UnwrapNoRef** does not increment the reference count for this new pointer to the unwrapped store object, after successfully calling **UnwrapNoRef**, you should call [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) to maintain the reference count.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="55277-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55277-116">See also</span></span>



[<span data-ttu-id="55277-117">IProxyStoreObject</span><span class="sxs-lookup"><span data-stu-id="55277-117">IProxyStoreObject</span></span>](iproxystoreobject.md)

