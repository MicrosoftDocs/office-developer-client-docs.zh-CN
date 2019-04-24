---
title: IProxyStoreObject
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject
api_type:
- COM
ms.assetid: 567bede4-39a3-bfb4-af85-ba678e2cf4a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 485d3f3cd4b6be4748a2ebf2ba0d0b71f691478f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315517"
---
# <a name="iproxystoreobject"></a><span data-ttu-id="480a9-103">IProxyStoreObject</span><span class="sxs-lookup"><span data-stu-id="480a9-103">IProxyStoreObject</span></span>

  
  
<span data-ttu-id="480a9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="480a9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="480a9-105">提供已解开的 Internet 邮件访问协议 (IMAP) 存储对象, 并允许访问个人文件夹文件 (PST) 中的项目, 而无需调用同步并下载这些项目。</span><span class="sxs-lookup"><span data-stu-id="480a9-105">Provides an Internet Message Access Protocol (IMAP) store object that has been unwrapped and that allows access to items in the Personal Folders file (PST) without invoking synchronization and downloading the items.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="480a9-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="480a9-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="480a9-107">继承自:</span><span class="sxs-lookup"><span data-stu-id="480a9-107">Inherited from:</span></span>  <br/> |[<span data-ttu-id="480a9-108">IUnknown</span><span class="sxs-lookup"><span data-stu-id="480a9-108">IUnknown</span></span>](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) <br/> |
|<span data-ttu-id="480a9-109">提供者:</span><span class="sxs-lookup"><span data-stu-id="480a9-109">Provided By:</span></span>  <br/> |<span data-ttu-id="480a9-110">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="480a9-110">Message store provider</span></span>  <br/> |
|<span data-ttu-id="480a9-111">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="480a9-111">Interface identifier:</span></span>  <br/> |<span data-ttu-id="480a9-112">**IID_IProxyStoreObject**</span><span class="sxs-lookup"><span data-stu-id="480a9-112">**IID_IProxyStoreObject**</span></span> <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="480a9-113">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="480a9-113">Vtable order</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="480a9-114">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="480a9-114">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="480a9-115">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="480a9-115">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="480a9-116">IProxyStoreObject::UnwrapNoRef</span><span class="sxs-lookup"><span data-stu-id="480a9-116">IProxyStoreObject::UnwrapNoRef</span></span>](iproxystoreobject-unwrapnoref.md) <br/> |<span data-ttu-id="480a9-117">获取一个指向未解包的 IMAP 存储区的指针。</span><span class="sxs-lookup"><span data-stu-id="480a9-117">Gets a pointer to an unwrapped IMAP store.</span></span>  <br/> |
| <span data-ttu-id="480a9-118">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="480a9-118">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="480a9-119">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="480a9-119">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="480a9-120">注解</span><span class="sxs-lookup"><span data-stu-id="480a9-120">Remarks</span></span>

<span data-ttu-id="480a9-121">调用[IUnknown::](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)源邮件存储上的 QueryInterface, 以获取**IProxyStoreObject**接口。</span><span class="sxs-lookup"><span data-stu-id="480a9-121">Call [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) on the source message store to obtain the **IProxyStoreObject** interface.</span></span> <span data-ttu-id="480a9-122">然后, 调用**IProxyStoreObject:: UnwrapNoRef**获取未包装的 store 对象。</span><span class="sxs-lookup"><span data-stu-id="480a9-122">Then call **IProxyStoreObject::UnwrapNoRef** to obtain the unwrapped store object.</span></span> <span data-ttu-id="480a9-123">如果**QueryInterface**返回错误**MAPI_E_INTERFACE_NOT_SUPPORTED**, 则存储尚未被包装。</span><span class="sxs-lookup"><span data-stu-id="480a9-123">If **QueryInterface** returns the error **MAPI_E_INTERFACE_NOT_SUPPORTED**, then the store has not been wrapped.</span></span> 
  
<span data-ttu-id="480a9-124">由于**UnwrapNoRef**不会将此新指针的引用计数增加到已解包的 store 对象, 因此在成功调用**UnwrapNoRef**后, 应调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)来维护引用计数。</span><span class="sxs-lookup"><span data-stu-id="480a9-124">Because **UnwrapNoRef** does not increment the reference count for this new pointer to the unwrapped store object, after successfully calling **UnwrapNoRef**, you should call [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) to maintain the reference count.</span></span> 
  

