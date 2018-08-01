---
title: PROP_ACCT_USER_EMAIL_ADDR
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fe447899-d37a-4775-a09d-13ba3a878008
description: 指定的帐户的电子邮件地址。
ms.openlocfilehash: 7d0bbba2dcb104326c360da6a10f3e19d1740e46
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774440"
---
# <a name="propacctuseremailaddr"></a><span data-ttu-id="ac191-103">PROP_ACCT_USER_EMAIL_ADDR</span><span class="sxs-lookup"><span data-stu-id="ac191-103">PROP_ACCT_USER_EMAIL_ADDR</span></span>

<span data-ttu-id="ac191-104">指定的帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ac191-104">Specifies the email address for the account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ac191-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="ac191-105">Quick info</span></span>

<span data-ttu-id="ac191-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="ac191-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac191-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="ac191-107">Identifier:</span></span>  <br/> |<span data-ttu-id="ac191-108">0x000C</span><span class="sxs-lookup"><span data-stu-id="ac191-108">0x000C</span></span>  <br/> |
|<span data-ttu-id="ac191-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="ac191-109">Property type:</span></span>  <br/> |<span data-ttu-id="ac191-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ac191-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ac191-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="ac191-111">Property tag:</span></span>  <br/> |<span data-ttu-id="ac191-112">0x000C001F</span><span class="sxs-lookup"><span data-stu-id="ac191-112">0x000C001F</span></span>  <br/> |
|<span data-ttu-id="ac191-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="ac191-113">Access:</span></span>  <br/> |<span data-ttu-id="ac191-114">读/写</span><span class="sxs-lookup"><span data-stu-id="ac191-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac191-115">备注</span><span class="sxs-lookup"><span data-stu-id="ac191-115">Remarks</span></span>

 <span data-ttu-id="ac191-116">**PROP_ACCT_USER_EMAIL_ADDR**不应存在于每个帐户上。</span><span class="sxs-lookup"><span data-stu-id="ac191-116">**PROP_ACCT_USER_EMAIL_ADDR** is not expected to exist on every account.</span></span> <span data-ttu-id="ac191-117">例如，Exchange 帐户可以具有[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md)但未为**PROP_ACCT_USER_EMAIL_ADDR**，而对于 SMTP/POP3 帐户，这种情况将被颠倒。</span><span class="sxs-lookup"><span data-stu-id="ac191-117">For example, an Exchange account could have [PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) but not **PROP_ACCT_USER_EMAIL_ADDR**, while for an SMTP/POP3 account, the situation is reversed.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac191-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac191-118">See also</span></span>

- [<span data-ttu-id="ac191-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="ac191-119">About the Account Management API</span></span>](about-the-account-management-api.md)

