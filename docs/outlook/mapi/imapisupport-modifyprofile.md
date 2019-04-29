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
# <a name="imapisupportmodifyprofile"></a><span data-ttu-id="141db-103">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="141db-103">IMAPISupport::ModifyProfile</span></span>

  
  
<span data-ttu-id="141db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="141db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="141db-105">对邮件存储库配置文件部分进行永久性更改。</span><span class="sxs-lookup"><span data-stu-id="141db-105">Makes changes to a message store profile section permanent.</span></span>
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="141db-106">参数</span><span class="sxs-lookup"><span data-stu-id="141db-106">Parameters</span></span>

 <span data-ttu-id="141db-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="141db-107">_ulFlags_</span></span>
  
> <span data-ttu-id="141db-108">实时指示邮件存储类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="141db-108">[in] A bitmask of flags that indicates the type of message store.</span></span> <span data-ttu-id="141db-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="141db-109">The following flag can be set:</span></span>
    
<span data-ttu-id="141db-110">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="141db-110">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="141db-111">邮件存储区是临时的, 不应添加到邮件存储库表中。</span><span class="sxs-lookup"><span data-stu-id="141db-111">The message store is temporary and should not be added to the message store table.</span></span> <span data-ttu-id="141db-112">如果设置了 MDB_TEMPORARY, 则**ModifyProfile**将立即返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="141db-112">When MDB_TEMPORARY is set, **ModifyProfile** returns S_OK immediately.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="141db-113">返回值</span><span class="sxs-lookup"><span data-stu-id="141db-113">Return value</span></span>

<span data-ttu-id="141db-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="141db-114">S_OK</span></span> 
  
> <span data-ttu-id="141db-115">对配置文件部分所做的更改已成功。</span><span class="sxs-lookup"><span data-stu-id="141db-115">The changes to the profile section were successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="141db-116">说明</span><span class="sxs-lookup"><span data-stu-id="141db-116">Remarks</span></span>

<span data-ttu-id="141db-117">为邮件存储提供程序支持对象实现了**IMAPISupport:: ModifyProfile**方法。</span><span class="sxs-lookup"><span data-stu-id="141db-117">The **IMAPISupport::ModifyProfile** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="141db-118">邮件存储提供程序调用**ModifyProfile**以提示 MAPI 修改其配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="141db-118">Message store providers call **ModifyProfile** to prompt MAPI to modify their profile information.</span></span> 
  
 <span data-ttu-id="141db-119">**ModifyProfile**将与调用提供程序关联的配置文件节添加到已安装的邮件存储提供程序资源列表中。</span><span class="sxs-lookup"><span data-stu-id="141db-119">**ModifyProfile** adds the profile section that is associated with the calling provider to the list of installed message store provider resources.</span></span> <span data-ttu-id="141db-120">这会使邮件存储在邮件存储表中列出, 该表可通过[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)方法供客户端使用, 并在不显示对话框的情况下打开。</span><span class="sxs-lookup"><span data-stu-id="141db-120">This causes the message store to be listed in the message store table, which is available to clients through the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method, and to be opened without the display of a dialog box.</span></span> 
  
<span data-ttu-id="141db-121">如果设置了 MDB_TEMPORARY 标志, MAPI 将不执行任何操作, 并且方法将立即返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="141db-121">If the MDB_TEMPORARY flag is set, MAPI does nothing and the method returns immediately with S_OK.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="141db-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="141db-122">See also</span></span>



[<span data-ttu-id="141db-123">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="141db-123">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="141db-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="141db-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

