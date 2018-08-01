---
title: PROP_MAPI_EMSMDB_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8e5b42e3-844f-488c-ba6f-b74c447b1d59
description: 表示包含 Exchange 帐户的 UID ACCT_BIN 结构。
ms.openlocfilehash: 05e2e61601a08e0cb6f6dc99d265f12a10b19d3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774457"
---
# <a name="propmapiemsmdbuid"></a><span data-ttu-id="2361b-103">PROP_MAPI_EMSMDB_UID</span><span class="sxs-lookup"><span data-stu-id="2361b-103">PROP_MAPI_EMSMDB_UID</span></span>

<span data-ttu-id="2361b-104">表示包含 Exchange 帐户的 UID [ACCT_BIN](acct_bin.md)结构。</span><span class="sxs-lookup"><span data-stu-id="2361b-104">Represents an [ACCT_BIN](acct_bin.md) structure that contains the UID of an Exchange account.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="2361b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="2361b-105">Quick info</span></span>

<span data-ttu-id="2361b-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="2361b-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2361b-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="2361b-107">Identifier:</span></span>  <br/> |<span data-ttu-id="2361b-108">0x2009</span><span class="sxs-lookup"><span data-stu-id="2361b-108">0x2009</span></span>  <br/> |
|<span data-ttu-id="2361b-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="2361b-109">Property type:</span></span>  <br/> |<span data-ttu-id="2361b-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2361b-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2361b-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="2361b-111">Property tag:</span></span>  <br/> |<span data-ttu-id="2361b-112">0x20090102</span><span class="sxs-lookup"><span data-stu-id="2361b-112">0x20090102</span></span>  <br/> |
|<span data-ttu-id="2361b-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="2361b-113">Access:</span></span>  <br/> |<span data-ttu-id="2361b-114">只读</span><span class="sxs-lookup"><span data-stu-id="2361b-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2361b-115">说明</span><span class="sxs-lookup"><span data-stu-id="2361b-115">Remarks</span></span>

<span data-ttu-id="2361b-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="2361b-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span>
  
<span data-ttu-id="2361b-117">使用[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)验证帐户是 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="2361b-117">Use [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) to verify if the account is an Exchange account.</span></span> <span data-ttu-id="2361b-118">如果是，**属性\_MAPI_EMSMDB_UID**是包含**emsmdbUID**，这是 Exchange 帐户的唯一 ID， **ACCT_BIN** 。</span><span class="sxs-lookup"><span data-stu-id="2361b-118">If it is, **PROP\_MAPI_EMSMDB_UID** is an **ACCT_BIN** that contains the **emsmdbUID**, which is the unique ID, for the Exchange account.</span></span> <span data-ttu-id="2361b-119">如果该帐户不是 Exchange 帐户，则此属性未定义。</span><span class="sxs-lookup"><span data-stu-id="2361b-119">If the account is not an Exchange account, this property is undefined.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2361b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2361b-120">See also</span></span>

- [<span data-ttu-id="2361b-121">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="2361b-121">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="2361b-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="2361b-122">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="2361b-123">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="2361b-123">Using Multiple Exchange Accounts</span></span>](http://msdn.microsoft.com/library/4e1804bf-4c50-4942-a7ab-9a8caf1be7e5%28Office.15%29.aspx)  
- [<span data-ttu-id="2361b-124">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="2361b-124">PidTagExchangeProfileSectionId Canonical Property</span></span>](http://msdn.microsoft.com/library/4ad2f417-be8f-4fc8-9321-82097289074b%28Office.15%29.aspx)

