---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个唯一标识创建帐户的配置文件中的帐户的标识符。
ms.openlocfilehash: dcb0a7935b9b764c44088971a1acb1f3647cbdb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407163"
---
# <a name="prop_acct_id"></a><span data-ttu-id="e544e-103">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="e544e-103">PROP_ACCT_ID</span></span>

<span data-ttu-id="e544e-104">返回一个唯一标识创建帐户的配置文件中的帐户的标识符。</span><span class="sxs-lookup"><span data-stu-id="e544e-104">Returns an identifier that uniquely identifies an account within the profile in which the account is created.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e544e-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="e544e-105">Quick info</span></span>

<span data-ttu-id="e544e-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="e544e-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e544e-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="e544e-107">Identifier:</span></span>  <br/> |<span data-ttu-id="e544e-108">0x0001</span><span class="sxs-lookup"><span data-stu-id="e544e-108">0x0001</span></span>  <br/> |
|<span data-ttu-id="e544e-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="e544e-109">Property type:</span></span>  <br/> |<span data-ttu-id="e544e-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e544e-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e544e-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="e544e-111">Property tag:</span></span>  <br/> |<span data-ttu-id="e544e-112">0x00010003</span><span class="sxs-lookup"><span data-stu-id="e544e-112">0x00010003</span></span>  <br/> |
|<span data-ttu-id="e544e-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="e544e-113">Access:</span></span>  <br/> |<span data-ttu-id="e544e-114">只读</span><span class="sxs-lookup"><span data-stu-id="e544e-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e544e-115">备注</span><span class="sxs-lookup"><span data-stu-id="e544e-115">Remarks</span></span>

<span data-ttu-id="e544e-116">使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。</span><span class="sxs-lookup"><span data-stu-id="e544e-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="e544e-117">如果客户端尝试设置此属性，则此属性返回 E_OLK_PROP_READ_ONLY **。**</span><span class="sxs-lookup"><span data-stu-id="e544e-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
<span data-ttu-id="e544e-118">此属性不同于 [PROP_ACCT_MINI_UID，](prop_acct_mini_uid.md) 因为其值仅在创建帐户的配置文件内的所有帐户之间是唯一的，而 **PROP \_ ACCT_MINI_UID** 用于唯一标识创建帐户的配置文件内外的帐户。</span><span class="sxs-lookup"><span data-stu-id="e544e-118">This property is different from [PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) in that its value is unique only among all the accounts within that profile in which the account was created, whereas **PROP\_ACCT_MINI_UID** uniquely identifies the account within and outside of the profile in which the account was created.</span></span> <span data-ttu-id="e544e-119">当具有这些属性的邮件漫游到具有不同 Outlook 配置文件和一组不同帐户的第二台计算机时 **，PROP_ACCT_ID** 可能会与第二台计算机的配置文件中的帐户发生冲突，**并且 PROP_ACCT_MINI_UID** 可以唯一地标识原始配置文件中的原始帐户。</span><span class="sxs-lookup"><span data-stu-id="e544e-119">When a message with these properties roams onto a second computer with a different Outlook profile and different set of accounts, **PROP_ACCT_ID** can possibly conflict with an account in the profile of the second computer, and **PROP_ACCT_MINI_UID** can uniquely identify the original account in the original profile.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e544e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e544e-120">See also</span></span>

- [<span data-ttu-id="e544e-121">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="e544e-121">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="e544e-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="e544e-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

