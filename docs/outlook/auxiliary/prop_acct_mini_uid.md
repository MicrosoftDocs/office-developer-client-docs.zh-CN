---
title: PROP_ACCT_MINI_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 30d8268e-0c64-401d-8799-e8e1ba78b88f
description: 返回 Outlook 配置文件之间都是唯一的帐户标识符。
ms.openlocfilehash: 9b2e30c0f57a54af219e68a8c2fe91e5dba4ddbe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774436"
---
# <a name="propacctminiuid"></a><span data-ttu-id="066d9-103">PROP_ACCT_MINI_UID</span><span class="sxs-lookup"><span data-stu-id="066d9-103">PROP_ACCT_MINI_UID</span></span>

<span data-ttu-id="066d9-104">返回 Outlook 配置文件之间都是唯一的帐户标识符。</span><span class="sxs-lookup"><span data-stu-id="066d9-104">Returns an account identifier that is unique across Outlook profiles.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="066d9-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="066d9-105">Quick info</span></span>

<span data-ttu-id="066d9-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="066d9-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="066d9-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="066d9-107">Identifier:</span></span>  <br/> |<span data-ttu-id="066d9-108">0x0003</span><span class="sxs-lookup"><span data-stu-id="066d9-108">0x0003</span></span>  <br/> |
|<span data-ttu-id="066d9-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="066d9-109">Property type:</span></span>  <br/> |<span data-ttu-id="066d9-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="066d9-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="066d9-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="066d9-111">Property tag:</span></span>  <br/> |<span data-ttu-id="066d9-112">0x00030003</span><span class="sxs-lookup"><span data-stu-id="066d9-112">0x00030003</span></span>  <br/> |
|<span data-ttu-id="066d9-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="066d9-113">Access:</span></span>  <br/> |<span data-ttu-id="066d9-114">只读</span><span class="sxs-lookup"><span data-stu-id="066d9-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="066d9-115">备注</span><span class="sxs-lookup"><span data-stu-id="066d9-115">Remarks</span></span>

<span data-ttu-id="066d9-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="066d9-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="066d9-117">如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="066d9-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
<span data-ttu-id="066d9-118">此属性是不同[PROP_ACCT_ID](prop_acct_id.md) ，其值唯一标识的帐户内部和外部的配置文件，在其中创建该帐户，而**PROP_ACCT_ID**是仅唯一的一个配置文件中的所有帐户在其中创建该帐户。</span><span class="sxs-lookup"><span data-stu-id="066d9-118">This property is different from [PROP_ACCT_ID](prop_acct_id.md) in that its value uniquely identifies the account within and outside of the profile in which the account was created, whereas **PROP_ACCT_ID** is unique only among all the accounts within that one profile in which the account was created.</span></span> <span data-ttu-id="066d9-119">当包含这些属性的消息漫游拖放到不同的 Outlook 配置文件的帐户的不同组与另一台计算机上时， **PROP_ACCT_MINI_UID**可以唯一标识原始的配置文件中的原始帐户。</span><span class="sxs-lookup"><span data-stu-id="066d9-119">When a message with these properties roams onto a second computer with a different Outlook profile and different set of accounts, **PROP_ACCT_MINI_UID** can uniquely identify the original account in the original profile.</span></span> <span data-ttu-id="066d9-120">但是， **PROP_ACCT_ID**可以使用第二台计算机的配置文件中的帐户可能冲突。</span><span class="sxs-lookup"><span data-stu-id="066d9-120">However, **PROP_ACCT_ID** can possibly conflict with an account in the profile of the second computer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="066d9-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="066d9-121">See also</span></span>

- [<span data-ttu-id="066d9-122">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="066d9-122">PROP_ACCT_ID</span></span>](prop_acct_id.md)  
- [<span data-ttu-id="066d9-123">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="066d9-123">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="066d9-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="066d9-124">Constants (Account management API)</span></span>](constants-account-management-api.md)

