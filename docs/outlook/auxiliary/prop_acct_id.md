---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个唯一标识在其中创建该帐户的配置文件中的帐户的标识符。
ms.openlocfilehash: a4ae193b89132ea718e16aec82f592205f9771c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774435"
---
# <a name="propacctid"></a><span data-ttu-id="8c25c-103">PROP_ACCT_ID</span><span class="sxs-lookup"><span data-stu-id="8c25c-103">PROP_ACCT_ID</span></span>

<span data-ttu-id="8c25c-104">返回一个唯一标识在其中创建该帐户的配置文件中的帐户的标识符。</span><span class="sxs-lookup"><span data-stu-id="8c25c-104">Returns an identifier that uniquely identifies an account within the profile in which the account is created.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8c25c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8c25c-105">Quick info</span></span>

<span data-ttu-id="8c25c-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="8c25c-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8c25c-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="8c25c-107">Identifier:</span></span>  <br/> |<span data-ttu-id="8c25c-108">0x0001</span><span class="sxs-lookup"><span data-stu-id="8c25c-108">0x0001</span></span>  <br/> |
|<span data-ttu-id="8c25c-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="8c25c-109">Property type:</span></span>  <br/> |<span data-ttu-id="8c25c-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8c25c-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8c25c-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="8c25c-111">Property tag:</span></span>  <br/> |<span data-ttu-id="8c25c-112">0x00010003</span><span class="sxs-lookup"><span data-stu-id="8c25c-112">0x00010003</span></span>  <br/> |
|<span data-ttu-id="8c25c-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="8c25c-113">Access:</span></span>  <br/> |<span data-ttu-id="8c25c-114">只读</span><span class="sxs-lookup"><span data-stu-id="8c25c-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c25c-115">说明</span><span class="sxs-lookup"><span data-stu-id="8c25c-115">Remarks</span></span>

<span data-ttu-id="8c25c-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="8c25c-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="8c25c-117">如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="8c25c-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
<span data-ttu-id="8c25c-118">此属性是不同[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) ，其值是仅唯一在其中创建该帐户，该配置文件中的所有帐户，而**属性\_ACCT_MINI_UID**唯一标识中的帐户和以外的在其中创建该帐户的配置文件。</span><span class="sxs-lookup"><span data-stu-id="8c25c-118">This property is different from [PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) in that its value is unique only among all the accounts within that profile in which the account was created, whereas **PROP\_ACCT_MINI_UID** uniquely identifies the account within and outside of the profile in which the account was created.</span></span> <span data-ttu-id="8c25c-119">当包含这些属性的消息漫游到其他 Outlook 配置文件的第二个计算机和组不同的帐户， **PROP_ACCT_ID**可以可能发生冲突的第二台计算机和**PROP_ACCT_MINI_UID**的配置文件中的帐户可以唯一标识原始的配置文件中的原始帐户。</span><span class="sxs-lookup"><span data-stu-id="8c25c-119">When a message with these properties roams onto a second computer with a different Outlook profile and different set of accounts, **PROP_ACCT_ID** can possibly conflict with an account in the profile of the second computer, and **PROP_ACCT_MINI_UID** can uniquely identify the original account in the original profile.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8c25c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c25c-120">See also</span></span>

- [<span data-ttu-id="8c25c-121">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="8c25c-121">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="8c25c-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="8c25c-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

