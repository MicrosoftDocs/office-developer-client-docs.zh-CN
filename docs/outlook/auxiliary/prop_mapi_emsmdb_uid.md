---
title: PROP_MAPI_EMSMDB_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 8e5b42e3-844f-488c-ba6f-b74c447b1d59
description: 表示包含 Exchange 帐户的 UID 的 ACCT_BIN 结构。
ms.openlocfilehash: 6bb529da82cc24e41ddc70c5031f84050a2ece25
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326549"
---
# <a name="propmapiemsmdbuid"></a><span data-ttu-id="25f88-103">PROP_MAPI_EMSMDB_UID</span><span class="sxs-lookup"><span data-stu-id="25f88-103">PROP_MAPI_EMSMDB_UID</span></span>

<span data-ttu-id="25f88-104">表示包含 Exchange 帐户的 UID 的[ACCT_BIN](acct_bin.md)结构。</span><span class="sxs-lookup"><span data-stu-id="25f88-104">Represents an [ACCT_BIN](acct_bin.md) structure that contains the UID of an Exchange account.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="25f88-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="25f88-105">Quick info</span></span>

<span data-ttu-id="25f88-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="25f88-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="25f88-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="25f88-107">Identifier:</span></span>  <br/> |<span data-ttu-id="25f88-108">0x2009</span><span class="sxs-lookup"><span data-stu-id="25f88-108">0x2009</span></span>  <br/> |
|<span data-ttu-id="25f88-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="25f88-109">Property type:</span></span>  <br/> |<span data-ttu-id="25f88-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="25f88-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="25f88-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="25f88-111">Property tag:</span></span>  <br/> |<span data-ttu-id="25f88-112">0x20090102</span><span class="sxs-lookup"><span data-stu-id="25f88-112">0x20090102</span></span>  <br/> |
|<span data-ttu-id="25f88-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="25f88-113">Access:</span></span>  <br/> |<span data-ttu-id="25f88-114">只读</span><span class="sxs-lookup"><span data-stu-id="25f88-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="25f88-115">注解</span><span class="sxs-lookup"><span data-stu-id="25f88-115">Remarks</span></span>

<span data-ttu-id="25f88-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="25f88-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span>
  
<span data-ttu-id="25f88-117">使用[PROP_ACCT_IS_EXCH](prop_acct_is_exch.md)验证帐户是否为 Exchange 帐户。</span><span class="sxs-lookup"><span data-stu-id="25f88-117">Use [PROP_ACCT_IS_EXCH](prop_acct_is_exch.md) to verify if the account is an Exchange account.</span></span> <span data-ttu-id="25f88-118">如果是, 则**\_MAPI_EMSMDB_UID**是一个**ACCT_BIN** , 其中包含 Exchange 帐户的**emsmdbUID**, 即唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="25f88-118">If it is, **PROP\_MAPI_EMSMDB_UID** is an **ACCT_BIN** that contains the **emsmdbUID**, which is the unique ID, for the Exchange account.</span></span> <span data-ttu-id="25f88-119">如果帐户不是 Exchange 帐户, 则此属性未定义。</span><span class="sxs-lookup"><span data-stu-id="25f88-119">If the account is not an Exchange account, this property is undefined.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25f88-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25f88-120">See also</span></span>

- [<span data-ttu-id="25f88-121">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="25f88-121">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="25f88-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="25f88-122">Constants (Account management API)</span></span>](constants-account-management-api.md)
- [<span data-ttu-id="25f88-123">使用多个 Exchange 帐户</span><span class="sxs-lookup"><span data-stu-id="25f88-123">Using Multiple Exchange Accounts</span></span>](https://msdn.microsoft.com/library/4e1804bf-4c50-4942-a7ab-9a8caf1be7e5%28Office.15%29.aspx)  
- [<span data-ttu-id="25f88-124">PidTagExchangeProfileSectionId 规范属性</span><span class="sxs-lookup"><span data-stu-id="25f88-124">PidTagExchangeProfileSectionId Canonical Property</span></span>](https://msdn.microsoft.com/library/4ad2f417-be8f-4fc8-9321-82097289074b%28Office.15%29.aspx)

