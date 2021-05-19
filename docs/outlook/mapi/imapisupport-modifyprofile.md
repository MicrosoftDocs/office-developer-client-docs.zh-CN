---
title: IMAPISupportModifyProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyProfile
api_type:
- COM
ms.assetid: 33bef4ea-d6c0-4455-b95d-4b29edb9c0bc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4c296b12d2dc98c4ff8d94349298e9dda0fb9409
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419987"
---
# <a name="imapisupportmodifyprofile"></a><span data-ttu-id="2ee0d-103">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="2ee0d-103">IMAPISupport::ModifyProfile</span></span>

  
  
<span data-ttu-id="2ee0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ee0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ee0d-105">永久更改邮件存储配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-105">Makes changes to a message store profile section permanent.</span></span>
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="2ee0d-106">参数</span><span class="sxs-lookup"><span data-stu-id="2ee0d-106">Parameters</span></span>

 <span data-ttu-id="2ee0d-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2ee0d-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2ee0d-108">[in]指示邮件存储类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-108">[in] A bitmask of flags that indicates the type of message store.</span></span> <span data-ttu-id="2ee0d-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2ee0d-109">The following flag can be set:</span></span>
    
<span data-ttu-id="2ee0d-110">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="2ee0d-110">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="2ee0d-111">邮件存储是临时的，不应添加到邮件存储表中。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-111">The message store is temporary and should not be added to the message store table.</span></span> <span data-ttu-id="2ee0d-112">设置MDB_TEMPORARY时 **，ModifyProfile** 将立即S_OK返回。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-112">When MDB_TEMPORARY is set, **ModifyProfile** returns S_OK immediately.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2ee0d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="2ee0d-113">Return value</span></span>

<span data-ttu-id="2ee0d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ee0d-114">S_OK</span></span> 
  
> <span data-ttu-id="2ee0d-115">对配置文件部分所做的更改已成功。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-115">The changes to the profile section were successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2ee0d-116">备注</span><span class="sxs-lookup"><span data-stu-id="2ee0d-116">Remarks</span></span>

<span data-ttu-id="2ee0d-117">**IMAPISupport：：ModifyProfile** 方法为邮件存储提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-117">The **IMAPISupport::ModifyProfile** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="2ee0d-118">邮件存储提供程序调用 **ModifyProfile** 以提示 MAPI 修改其配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-118">Message store providers call **ModifyProfile** to prompt MAPI to modify their profile information.</span></span> 
  
 <span data-ttu-id="2ee0d-119">**ModifyProfile** 将与调用提供程序关联的配置文件节添加到已安装的邮件存储提供程序资源列表中。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-119">**ModifyProfile** adds the profile section that is associated with the calling provider to the list of installed message store provider resources.</span></span> <span data-ttu-id="2ee0d-120">这将导致消息存储表中列出的消息存储，该表通过 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法对客户端可用，并且打开时不显示对话框。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-120">This causes the message store to be listed in the message store table, which is available to clients through the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method, and to be opened without the display of a dialog box.</span></span> 
  
<span data-ttu-id="2ee0d-121">如果设置了 MDB_TEMPORARY 标志，MAPI 不执行任何操作，并且该方法将立即返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2ee0d-121">If the MDB_TEMPORARY flag is set, MAPI does nothing and the method returns immediately with S_OK.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ee0d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ee0d-122">See also</span></span>



[<span data-ttu-id="2ee0d-123">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="2ee0d-123">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="2ee0d-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2ee0d-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

