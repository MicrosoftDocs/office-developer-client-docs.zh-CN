---
title: PROP_MAPI_TRANSPORT_FLAGS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 12cfe096-6882-c0be-b248-87567cb71e83
description: 表示 Outlook 用于确定必要的同步任务并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
ms.openlocfilehash: 707306c3bfbeebdd18f82bacfc121274be08aa50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404524"
---
# <a name="propmapitransportflags"></a><span data-ttu-id="ff5df-103">PROP_MAPI_TRANSPORT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="ff5df-103">PROP_MAPI_TRANSPORT_FLAGS</span></span>

<span data-ttu-id="ff5df-104">表示 Outlook 用于确定必要的同步任务并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。</span><span class="sxs-lookup"><span data-stu-id="ff5df-104">Represents transport settings that Outlook uses to determine the necessary synchronization tasks and to disable the user interface (UI) elements that the account does not support.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ff5df-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="ff5df-105">Quick info</span></span>

<span data-ttu-id="ff5df-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="ff5df-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff5df-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="ff5df-107">Identifier:</span></span>  <br/> |<span data-ttu-id="ff5df-108">0x2010</span><span class="sxs-lookup"><span data-stu-id="ff5df-108">0x2010</span></span>  <br/> |
|<span data-ttu-id="ff5df-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="ff5df-109">Property type:</span></span>  <br/> |<span data-ttu-id="ff5df-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ff5df-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ff5df-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="ff5df-111">Property tag:</span></span>  <br/> |<span data-ttu-id="ff5df-112">0x20100102</span><span class="sxs-lookup"><span data-stu-id="ff5df-112">0x20100102</span></span>  <br/> |
|<span data-ttu-id="ff5df-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="ff5df-113">Access:</span></span>  <br/> |<span data-ttu-id="ff5df-114">读/写</span><span class="sxs-lookup"><span data-stu-id="ff5df-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff5df-115">说明</span><span class="sxs-lookup"><span data-stu-id="ff5df-115">Remarks</span></span>

<span data-ttu-id="ff5df-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span><span class="sxs-lookup"><span data-stu-id="ff5df-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span></span>
  
<span data-ttu-id="ff5df-117">如果帐户只能发送邮件, 但无法接收邮件, 则返回**MAPIACCT_SEND_ONLY** 。</span><span class="sxs-lookup"><span data-stu-id="ff5df-117">Returns **MAPIACCT_SEND_ONLY** if the account can only send messages but cannot receive messages.</span></span> <span data-ttu-id="ff5df-118">在这种情况下, Outlook 禁用不适用于此类帐户的 ui (例如, 用于 "**发送/接收**" 的 ui)。</span><span class="sxs-lookup"><span data-stu-id="ff5df-118">In this case, Outlook disables UI that does not apply to this type of accounts (for example, the UI for **Send/Receive**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff5df-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff5df-119">See also</span></span>

- [<span data-ttu-id="ff5df-120">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="ff5df-120">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="ff5df-121">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="ff5df-121">Constants (Account management API)</span></span>](constants-account-management-api.md)

