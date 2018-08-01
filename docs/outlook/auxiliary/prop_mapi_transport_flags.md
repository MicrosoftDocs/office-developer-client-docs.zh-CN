---
title: PROP_MAPI_TRANSPORT_FLAGS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 12cfe096-6882-c0be-b248-87567cb71e83
description: 代表 Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。
ms.openlocfilehash: 95b61ea994557be76303f8b9b0541353b6ed13f6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774438"
---
# <a name="propmapitransportflags"></a><span data-ttu-id="6caaf-103">PROP_MAPI_TRANSPORT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6caaf-103">PROP_MAPI_TRANSPORT_FLAGS</span></span>

<span data-ttu-id="6caaf-104">代表 Outlook 使用以确定所需同步任务，并禁用该帐户不支持的用户界面 (UI) 元素的传输设置。</span><span class="sxs-lookup"><span data-stu-id="6caaf-104">Represents transport settings that Outlook uses to determine the necessary synchronization tasks and to disable the user interface (UI) elements that the account does not support.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6caaf-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="6caaf-105">Quick info</span></span>

<span data-ttu-id="6caaf-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="6caaf-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6caaf-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="6caaf-107">Identifier:</span></span>  <br/> |<span data-ttu-id="6caaf-108">0x2010</span><span class="sxs-lookup"><span data-stu-id="6caaf-108">0x2010</span></span>  <br/> |
|<span data-ttu-id="6caaf-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="6caaf-109">Property type:</span></span>  <br/> |<span data-ttu-id="6caaf-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6caaf-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6caaf-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="6caaf-111">Property tag:</span></span>  <br/> |<span data-ttu-id="6caaf-112">0x20100102</span><span class="sxs-lookup"><span data-stu-id="6caaf-112">0x20100102</span></span>  <br/> |
|<span data-ttu-id="6caaf-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="6caaf-113">Access:</span></span>  <br/> |<span data-ttu-id="6caaf-114">读/写</span><span class="sxs-lookup"><span data-stu-id="6caaf-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6caaf-115">备注</span><span class="sxs-lookup"><span data-stu-id="6caaf-115">Remarks</span></span>

<span data-ttu-id="6caaf-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span><span class="sxs-lookup"><span data-stu-id="6caaf-116">Get or set this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md) or [IOlkAccount::SetProp](iolkaccount-setprop.md), respectively.</span></span>
  
<span data-ttu-id="6caaf-117">返回**MAPIACCT_SEND_ONLY** ，如果该帐户只能发送消息，但无法接收消息。</span><span class="sxs-lookup"><span data-stu-id="6caaf-117">Returns **MAPIACCT_SEND_ONLY** if the account can only send messages but cannot receive messages.</span></span> <span data-ttu-id="6caaf-118">在这种情况下，Outlook 禁用不适用于这种类型的帐户 (例如，**发送/接收**的 UI) 的 UI。</span><span class="sxs-lookup"><span data-stu-id="6caaf-118">In this case, Outlook disables UI that does not apply to this type of accounts (for example, the UI for **Send/Receive**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6caaf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6caaf-119">See also</span></span>

- [<span data-ttu-id="6caaf-120">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="6caaf-120">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="6caaf-121">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="6caaf-121">Constants (Account management API)</span></span>](constants-account-management-api.md)

