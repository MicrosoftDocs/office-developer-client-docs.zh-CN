---
title: PROP_ACCT_MINI_UID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 30d8268e-0c64-401d-8799-e8e1ba78b88f
description: 返回一个帐户标识符, 该标识符在 Outlook 配置文件中是唯一的。
ms.openlocfilehash: 209f7dd89b8d947b999f2a068373aaf61a3e9784
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327627"
---
# <a name="propacctminiuid"></a><span data-ttu-id="1500d-103">PROP_ACCT_MINI_UID</span><span class="sxs-lookup"><span data-stu-id="1500d-103">PROP_ACCT_MINI_UID</span></span>

<span data-ttu-id="1500d-104">返回一个帐户标识符, 该标识符在 Outlook 配置文件中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1500d-104">Returns an account identifier that is unique across Outlook profiles.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="1500d-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="1500d-105">Quick info</span></span>

<span data-ttu-id="1500d-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="1500d-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1500d-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="1500d-107">Identifier:</span></span>  <br/> |<span data-ttu-id="1500d-108">0x0003</span><span class="sxs-lookup"><span data-stu-id="1500d-108">0x0003</span></span>  <br/> |
|<span data-ttu-id="1500d-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="1500d-109">Property type:</span></span>  <br/> |<span data-ttu-id="1500d-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1500d-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1500d-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="1500d-111">Property tag:</span></span>  <br/> |<span data-ttu-id="1500d-112">0x00030003</span><span class="sxs-lookup"><span data-stu-id="1500d-112">0x00030003</span></span>  <br/> |
|<span data-ttu-id="1500d-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="1500d-113">Access:</span></span>  <br/> |<span data-ttu-id="1500d-114">只读</span><span class="sxs-lookup"><span data-stu-id="1500d-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1500d-115">注解</span><span class="sxs-lookup"><span data-stu-id="1500d-115">Remarks</span></span>

<span data-ttu-id="1500d-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="1500d-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="1500d-117">如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="1500d-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
<span data-ttu-id="1500d-118">此属性与[PROP_ACCT_ID](prop_acct_id.md)的不同之处是, 它的值唯一标识在其中创建帐户的配置文件内和外部的帐户, 而**PROP_ACCT_ID**仅在一个配置文件中的所有帐户之间是唯一的帐户的创建时间。</span><span class="sxs-lookup"><span data-stu-id="1500d-118">This property is different from [PROP_ACCT_ID](prop_acct_id.md) in that its value uniquely identifies the account within and outside of the profile in which the account was created, whereas **PROP_ACCT_ID** is unique only among all the accounts within that one profile in which the account was created.</span></span> <span data-ttu-id="1500d-119">当具有这些属性的邮件将漫游到具有不同 Outlook 配置文件的另一台计算机和不同的帐户集时, **PROP_ACCT_MINI_UID**可以唯一地标识原始配置文件中的原始帐户。</span><span class="sxs-lookup"><span data-stu-id="1500d-119">When a message with these properties roams onto a second computer with a different Outlook profile and different set of accounts, **PROP_ACCT_MINI_UID** can uniquely identify the original account in the original profile.</span></span> <span data-ttu-id="1500d-120">但是, **PROP_ACCT_ID**可能会与第二台计算机的配置文件中的帐户发生冲突。</span><span class="sxs-lookup"><span data-stu-id="1500d-120">However, **PROP_ACCT_ID** can possibly conflict with an account in the profile of the second computer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1500d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1500d-121">See also</span></span>

- [<span data-ttu-id="1500d-122">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="1500d-122">PROP_ACCT_ID</span></span>](prop_acct_id.md)  
- [<span data-ttu-id="1500d-123">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="1500d-123">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="1500d-124">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="1500d-124">Constants (Account management API)</span></span>](constants-account-management-api.md)

