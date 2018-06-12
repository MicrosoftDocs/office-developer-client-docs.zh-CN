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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f6566f567c228b6416a64dbd58653561bb592e6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776040"
---
# <a name="iproxystoreobject"></a><span data-ttu-id="98714-103">IProxyStoreObject</span><span class="sxs-lookup"><span data-stu-id="98714-103">IProxyStoreObject</span></span>

  
  
<span data-ttu-id="98714-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="98714-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="98714-105">提供 Internet 消息访问协议 (IMAP) 存储对象的已解包并不调用同步和下载项目的情况下允许访问个人文件夹文件 (PST) 中的项。</span><span class="sxs-lookup"><span data-stu-id="98714-105">Provides an Internet Message Access Protocol (IMAP) store object that has been unwrapped and that allows access to items in the Personal Folders file (PST) without invoking synchronization and downloading the items.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="98714-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="98714-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="98714-107">继承：</span><span class="sxs-lookup"><span data-stu-id="98714-107">Inherited from:</span></span>  <br/> |[<span data-ttu-id="98714-108">IUnknown</span><span class="sxs-lookup"><span data-stu-id="98714-108">IUnknown</span></span>](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) <br/> |
|<span data-ttu-id="98714-109">供稿人：</span><span class="sxs-lookup"><span data-stu-id="98714-109">Provided By:</span></span>  <br/> |<span data-ttu-id="98714-110">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="98714-110">Message store provider</span></span>  <br/> |
|<span data-ttu-id="98714-111">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="98714-111">Interface identifier:</span></span>  <br/> |<span data-ttu-id="98714-112">**IID_IProxyStoreObject**</span><span class="sxs-lookup"><span data-stu-id="98714-112">**IID_IProxyStoreObject**</span></span> <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="98714-113">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="98714-113">Vtable order</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="98714-114">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="98714-114">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="98714-115">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="98714-115">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="98714-116">IProxyStoreObject::UnwrapNoRef</span><span class="sxs-lookup"><span data-stu-id="98714-116">IProxyStoreObject::UnwrapNoRef</span></span>](iproxystoreobject-unwrapnoref.md) <br/> |<span data-ttu-id="98714-117">获取一个指向解包 IMAP 存储区。</span><span class="sxs-lookup"><span data-stu-id="98714-117">Gets a pointer to an unwrapped IMAP store.</span></span>  <br/> |
| <span data-ttu-id="98714-118">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="98714-118">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="98714-119">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="98714-119">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98714-120">备注</span><span class="sxs-lookup"><span data-stu-id="98714-120">Remarks</span></span>

<span data-ttu-id="98714-121">对要获取**IProxyStoreObject**接口的源消息存储调用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="98714-121">Call [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) on the source message store to obtain the **IProxyStoreObject** interface.</span></span> <span data-ttu-id="98714-122">然后调用**IProxyStoreObject::UnwrapNoRef**获取解包的 store 对象。</span><span class="sxs-lookup"><span data-stu-id="98714-122">Then call **IProxyStoreObject::UnwrapNoRef** to obtain the unwrapped store object.</span></span> <span data-ttu-id="98714-123">如果**QueryInterface**返回错误**MAPI_E_INTERFACE_NOT_SUPPORTED**，然后存储不具有已包装。</span><span class="sxs-lookup"><span data-stu-id="98714-123">If **QueryInterface** returns the error **MAPI_E_INTERFACE_NOT_SUPPORTED**, then the store has not been wrapped.</span></span> 
  
<span data-ttu-id="98714-124">由于**UnwrapNoRef**不会增加到解包的存储对象，此新指针的引用计数成功调用**UnwrapNoRef**后，您应调用[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)维护引用计数。</span><span class="sxs-lookup"><span data-stu-id="98714-124">Because **UnwrapNoRef** does not increment the reference count for this new pointer to the unwrapped store object, after successfully calling **UnwrapNoRef**, you should call [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) to maintain the reference count.</span></span> 
  

