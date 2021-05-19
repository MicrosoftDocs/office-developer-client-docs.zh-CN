---
title: IMAPIFormFactoryLockServer
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory.LockServer
api_type:
- COM
ms.assetid: b9bd389a-6975-41a2-a2f4-e501312e434b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ab51b939651bc3c121f357545969d26832a19d19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342138"
---
# <a name="imapiformfactorylockserver"></a><span data-ttu-id="5bea5-103">IMAPIFormFactory::LockServer</span><span class="sxs-lookup"><span data-stu-id="5bea5-103">IMAPIFormFactory::LockServer</span></span>

  
  
<span data-ttu-id="5bea5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5bea5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5bea5-105">将打开的表单服务器保留到内存中。</span><span class="sxs-lookup"><span data-stu-id="5bea5-105">Keeps an open form server in memory.</span></span>
  
```cpp
HRESULT LockServer(
  ULONG ulFlags,
  ULONG fLockServer
);
```

## <a name="parameters"></a><span data-ttu-id="5bea5-106">参数</span><span class="sxs-lookup"><span data-stu-id="5bea5-106">Parameters</span></span>

 <span data-ttu-id="5bea5-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5bea5-107">_ulFlags_</span></span>
  
> <span data-ttu-id="5bea5-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="5bea5-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="5bea5-109">_fLockServer_</span><span class="sxs-lookup"><span data-stu-id="5bea5-109">_fLockServer_</span></span>
  
> <span data-ttu-id="5bea5-110">[in] **如果为 true，** 则增加锁定计数;否则为 **false**。</span><span class="sxs-lookup"><span data-stu-id="5bea5-110">[in] **true** to increment the lock count; otherwise, **false**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5bea5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5bea5-111">Return value</span></span>

<span data-ttu-id="5bea5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bea5-112">S_OK</span></span> 
  
> <span data-ttu-id="5bea5-113">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="5bea5-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5bea5-114">备注</span><span class="sxs-lookup"><span data-stu-id="5bea5-114">Remarks</span></span>

<span data-ttu-id="5bea5-115">表单查看器调用 **IMAPIFormFactory：：LockServer** 方法来将打开的表单服务器应用程序保持在内存中。</span><span class="sxs-lookup"><span data-stu-id="5bea5-115">Form viewers call the **IMAPIFormFactory::LockServer** method to keep an open form server application in memory.</span></span> <span data-ttu-id="5bea5-116">在频繁创建和释放表单时，将窗体服务器保留到内存中可提高性能。</span><span class="sxs-lookup"><span data-stu-id="5bea5-116">Keeping the form server in memory improves its performance when forms are frequently created and released.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5bea5-117">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5bea5-117">Notes to implementers</span></span>

<span data-ttu-id="5bea5-118">**IMAPIFormFactory：：LockServer** 方法与 [IClassFactory：：LockServer](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx)方法非常相似。</span><span class="sxs-lookup"><span data-stu-id="5bea5-118">The **IMAPIFormFactory::LockServer** method is very similar to the [IClassFactory::LockServer](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="5bea5-119">实质上 **，IMAPIFormFactory：：LockServer** 方法维护其调用次数的计数;只要该计数大于 0，该方法就可防止从内存中卸载表单服务器。</span><span class="sxs-lookup"><span data-stu-id="5bea5-119">Essentially, the **IMAPIFormFactory::LockServer** method maintains a count of how many times it has been called; as long as that count is greater than 0, the method prevents the form server from being unloaded from memory.</span></span> <span data-ttu-id="5bea5-120">可以使用 [CoLockObjectExternal](https://msdn.microsoft.com/library/ms680592%28VS.85%29.aspx) 函数来实现这一点。</span><span class="sxs-lookup"><span data-stu-id="5bea5-120">You can use the [CoLockObjectExternal](https://msdn.microsoft.com/library/ms680592%28VS.85%29.aspx) function to implement this.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5bea5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bea5-121">See also</span></span>



[<span data-ttu-id="5bea5-122">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5bea5-122">IMAPIFormFactory : IUnknown</span></span>](imapiformfactoryiunknown.md)

