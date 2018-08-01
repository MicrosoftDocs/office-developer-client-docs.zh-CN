---
title: PROP_ACCT_DELIVERY_STORE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5db43e9-687b-d467-1be1-3737e3f91c27
description: 表示默认送达存储的帐户的条目 ID。
ms.openlocfilehash: 72c5325e70a6e8b42ee433d8d674c2b2ea0c8398
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774425"
---
# <a name="propacctdeliverystore"></a><span data-ttu-id="f03c1-103">PROP_ACCT_DELIVERY_STORE</span><span class="sxs-lookup"><span data-stu-id="f03c1-103">PROP_ACCT_DELIVERY_STORE</span></span>

<span data-ttu-id="f03c1-104">表示默认送达存储的帐户的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="f03c1-104">Represents the Entry ID of the default delivery store for the account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f03c1-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="f03c1-105">Quick info</span></span>

<span data-ttu-id="f03c1-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="f03c1-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f03c1-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="f03c1-107">Identifier:</span></span>  <br/> |<span data-ttu-id="f03c1-108">0x0018</span><span class="sxs-lookup"><span data-stu-id="f03c1-108">0x0018</span></span>  <br/> |
|<span data-ttu-id="f03c1-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="f03c1-109">Property type:</span></span>  <br/> |<span data-ttu-id="f03c1-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f03c1-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f03c1-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="f03c1-111">Property tag:</span></span>  <br/> |<span data-ttu-id="f03c1-112">0x00180102</span><span class="sxs-lookup"><span data-stu-id="f03c1-112">0x00180102</span></span>  <br/> |
|<span data-ttu-id="f03c1-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="f03c1-113">Access:</span></span>  <br/> |<span data-ttu-id="f03c1-114">读/写</span><span class="sxs-lookup"><span data-stu-id="f03c1-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f03c1-115">备注</span><span class="sxs-lookup"><span data-stu-id="f03c1-115">Remarks</span></span>

<span data-ttu-id="f03c1-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span><span class="sxs-lookup"><span data-stu-id="f03c1-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span></span>
  
<span data-ttu-id="f03c1-117">设置为帐户的默认传递存储区的存储区之一是副作用的，启动 Outlook，Outlook 将创建搜索文件夹的存储如果用户已不存在，并列出在待办事项栏的存储。</span><span class="sxs-lookup"><span data-stu-id="f03c1-117">One of the side effects of setting a store as the default delivery store for an account is that when starting Outlook, Outlook creates search folders for that store if they do not already exist, and list the store in the To-Do Bar.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f03c1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f03c1-118">See also</span></span>

- [<span data-ttu-id="f03c1-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="f03c1-119">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="f03c1-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="f03c1-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

