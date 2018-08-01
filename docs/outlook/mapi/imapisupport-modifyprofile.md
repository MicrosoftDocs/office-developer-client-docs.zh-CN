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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 98e6331d5a9e52d5ae73ed12d8c045bdf226c2c4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775619"
---
# <a name="imapisupportmodifyprofile"></a><span data-ttu-id="323b0-103">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="323b0-103">IMAPISupport::ModifyProfile</span></span>

  
  
<span data-ttu-id="323b0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="323b0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="323b0-105">对做的更改一条消息存储永久的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="323b0-105">Makes changes to a message store profile section permanent.</span></span>
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="323b0-106">参数</span><span class="sxs-lookup"><span data-stu-id="323b0-106">Parameters</span></span>

 <span data-ttu-id="323b0-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="323b0-107">_ulFlags_</span></span>
  
> <span data-ttu-id="323b0-108">[in]存储一个位掩码的标志，指示邮件的类型。</span><span class="sxs-lookup"><span data-stu-id="323b0-108">[in] A bitmask of flags that indicates the type of message store.</span></span> <span data-ttu-id="323b0-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="323b0-109">The following flag can be set:</span></span>
    
<span data-ttu-id="323b0-110">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="323b0-110">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="323b0-111">消息存储库是临时，不应添加到消息存储表。</span><span class="sxs-lookup"><span data-stu-id="323b0-111">The message store is temporary and should not be added to the message store table.</span></span> <span data-ttu-id="323b0-112">当设置 MDB_TEMPORARY 时， **ModifyProfile**立即返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="323b0-112">When MDB_TEMPORARY is set, **ModifyProfile** returns S_OK immediately.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="323b0-113">返回值</span><span class="sxs-lookup"><span data-stu-id="323b0-113">Return value</span></span>

<span data-ttu-id="323b0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="323b0-114">S_OK</span></span> 
  
> <span data-ttu-id="323b0-115">对配置文件部分的更改都是成功的。</span><span class="sxs-lookup"><span data-stu-id="323b0-115">The changes to the profile section were successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="323b0-116">说明</span><span class="sxs-lookup"><span data-stu-id="323b0-116">Remarks</span></span>

<span data-ttu-id="323b0-117">消息存储提供程序支持对象的实现**IMAPISupport::ModifyProfile**方法。</span><span class="sxs-lookup"><span data-stu-id="323b0-117">The **IMAPISupport::ModifyProfile** method is implemented for message store provider support objects.</span></span> <span data-ttu-id="323b0-118">消息存储提供程序调用**ModifyProfile**提示 MAPI 修改其配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="323b0-118">Message store providers call **ModifyProfile** to prompt MAPI to modify their profile information.</span></span> 
  
 <span data-ttu-id="323b0-119">**ModifyProfile**添加到已安装的消息存储提供程序资源的列表的呼叫提供程序相关联的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="323b0-119">**ModifyProfile** adds the profile section that is associated with the calling provider to the list of installed message store provider resources.</span></span> <span data-ttu-id="323b0-120">此时会列出在消息存储表中，可供客户端通过[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法，并打开，也不显示的对话框中的消息存储。</span><span class="sxs-lookup"><span data-stu-id="323b0-120">This causes the message store to be listed in the message store table, which is available to clients through the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method, and to be opened without the display of a dialog box.</span></span> 
  
<span data-ttu-id="323b0-121">如果设置了 MDB_TEMPORARY 标志，MAPI 不执行任何操作并与 S_OK 立即返回的方法。</span><span class="sxs-lookup"><span data-stu-id="323b0-121">If the MDB_TEMPORARY flag is set, MAPI does nothing and the method returns immediately with S_OK.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="323b0-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="323b0-122">See also</span></span>



[<span data-ttu-id="323b0-123">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="323b0-123">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="323b0-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="323b0-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

