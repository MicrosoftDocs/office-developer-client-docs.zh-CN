---
title: PROP_ACCT_DELIVERY_STORE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5db43e9-687b-d467-1be1-3737e3f91c27
description: 代表帐户的默认传递存储的条目 ID。
ms.openlocfilehash: d803c539ec99da4d7fb31063f48237788f3ac3d9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327669"
---
# <a name="propacctdeliverystore"></a><span data-ttu-id="bebd2-103">PROP_ACCT_DELIVERY_STORE</span><span class="sxs-lookup"><span data-stu-id="bebd2-103">PROP_ACCT_DELIVERY_STORE</span></span>

<span data-ttu-id="bebd2-104">代表帐户的默认传递存储的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="bebd2-104">Represents the Entry ID of the default delivery store for the account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="bebd2-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="bebd2-105">Quick info</span></span>

<span data-ttu-id="bebd2-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="bebd2-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bebd2-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="bebd2-107">Identifier:</span></span>  <br/> |<span data-ttu-id="bebd2-108">0x0018</span><span class="sxs-lookup"><span data-stu-id="bebd2-108">0x0018</span></span>  <br/> |
|<span data-ttu-id="bebd2-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="bebd2-109">Property type:</span></span>  <br/> |<span data-ttu-id="bebd2-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="bebd2-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="bebd2-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="bebd2-111">Property tag:</span></span>  <br/> |<span data-ttu-id="bebd2-112">0x00180102</span><span class="sxs-lookup"><span data-stu-id="bebd2-112">0x00180102</span></span>  <br/> |
|<span data-ttu-id="bebd2-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="bebd2-113">Access:</span></span>  <br/> |<span data-ttu-id="bebd2-114">读/写</span><span class="sxs-lookup"><span data-stu-id="bebd2-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bebd2-115">注解</span><span class="sxs-lookup"><span data-stu-id="bebd2-115">Remarks</span></span>

<span data-ttu-id="bebd2-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span><span class="sxs-lookup"><span data-stu-id="bebd2-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span></span>
  
<span data-ttu-id="bebd2-117">将存储设置为帐户的默认传递存储的一个副作用是, 当启动 outlook 时, outlook 会为该存储创建搜索文件夹 (如果它们尚不存在), 并在待办栏中列出该存储区。</span><span class="sxs-lookup"><span data-stu-id="bebd2-117">One of the side effects of setting a store as the default delivery store for an account is that when starting Outlook, Outlook creates search folders for that store if they do not already exist, and list the store in the To-Do Bar.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bebd2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bebd2-118">See also</span></span>

- [<span data-ttu-id="bebd2-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="bebd2-119">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="bebd2-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="bebd2-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

