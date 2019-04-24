---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个标识符, 用于唯一标识在其中创建帐户的配置文件中的帐户。
ms.openlocfilehash: dcb0a7935b9b764c44088971a1acb1f3647cbdb0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327655"
---
# <a name="propacctid"></a><span data-ttu-id="90757-103">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="90757-103">PROP_ACCT_ID</span></span>

<span data-ttu-id="90757-104">返回一个标识符, 用于唯一标识在其中创建帐户的配置文件中的帐户。</span><span class="sxs-lookup"><span data-stu-id="90757-104">Returns an identifier that uniquely identifies an account within the profile in which the account is created.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="90757-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="90757-105">Quick info</span></span>

<span data-ttu-id="90757-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="90757-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="90757-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="90757-107">Identifier:</span></span>  <br/> |<span data-ttu-id="90757-108">0x0001</span><span class="sxs-lookup"><span data-stu-id="90757-108">0x0001</span></span>  <br/> |
|<span data-ttu-id="90757-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="90757-109">Property type:</span></span>  <br/> |<span data-ttu-id="90757-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="90757-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="90757-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="90757-111">Property tag:</span></span>  <br/> |<span data-ttu-id="90757-112">0x00010003</span><span class="sxs-lookup"><span data-stu-id="90757-112">0x00010003</span></span>  <br/> |
|<span data-ttu-id="90757-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="90757-113">Access:</span></span>  <br/> |<span data-ttu-id="90757-114">只读</span><span class="sxs-lookup"><span data-stu-id="90757-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90757-115">注解</span><span class="sxs-lookup"><span data-stu-id="90757-115">Remarks</span></span>

<span data-ttu-id="90757-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="90757-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="90757-117">如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="90757-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
<span data-ttu-id="90757-118">此属性与[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)的不同之处是, 它的值仅在创建帐户的配置文件中的所有帐户中是唯一的, 而属性**\_ACCT_MINI_UID**可唯一标识中的帐户和在其中创建帐户的配置文件之外。</span><span class="sxs-lookup"><span data-stu-id="90757-118">This property is different from [PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) in that its value is unique only among all the accounts within that profile in which the account was created, whereas **PROP\_ACCT_MINI_UID** uniquely identifies the account within and outside of the profile in which the account was created.</span></span> <span data-ttu-id="90757-119">当具有这些属性的邮件将使用不同的 Outlook 配置文件和不同的帐户集漫游到另一台计算机上时, **PROP_ACCT_ID**可能会与第二台计算机的配置文件中的帐户发生冲突, 并**PROP_ACCT_MINI_UID**可以唯一地标识原始配置文件中的原始帐户。</span><span class="sxs-lookup"><span data-stu-id="90757-119">When a message with these properties roams onto a second computer with a different Outlook profile and different set of accounts, **PROP_ACCT_ID** can possibly conflict with an account in the profile of the second computer, and **PROP_ACCT_MINI_UID** can uniquely identify the original account in the original profile.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="90757-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90757-120">See also</span></span>

- [<span data-ttu-id="90757-121">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="90757-121">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="90757-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="90757-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

