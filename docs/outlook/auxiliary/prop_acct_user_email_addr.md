---
title: PROP_ACCT_USER_EMAIL_ADDR
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fe447899-d37a-4775-a09d-13ba3a878008
description: 指定帐户的电子邮件地址。
ms.openlocfilehash: 115941fdf2fdec01da8d6bc1320ac6cdc0930ffa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436774"
---
# <a name="propacctuseremailaddr"></a><span data-ttu-id="0293b-103">PROP_ACCT_USER_EMAIL_ADDR</span><span class="sxs-lookup"><span data-stu-id="0293b-103">PROP_ACCT_USER_EMAIL_ADDR</span></span>

<span data-ttu-id="0293b-104">指定帐户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0293b-104">Specifies the email address for the account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0293b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="0293b-105">Quick info</span></span>

<span data-ttu-id="0293b-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="0293b-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0293b-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="0293b-107">Identifier:</span></span>  <br/> |<span data-ttu-id="0293b-108">0x000C</span><span class="sxs-lookup"><span data-stu-id="0293b-108">0x000C</span></span>  <br/> |
|<span data-ttu-id="0293b-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="0293b-109">Property type:</span></span>  <br/> |<span data-ttu-id="0293b-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0293b-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0293b-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="0293b-111">Property tag:</span></span>  <br/> |<span data-ttu-id="0293b-112">0x000C001F</span><span class="sxs-lookup"><span data-stu-id="0293b-112">0x000C001F</span></span>  <br/> |
|<span data-ttu-id="0293b-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="0293b-113">Access:</span></span>  <br/> |<span data-ttu-id="0293b-114">读/写</span><span class="sxs-lookup"><span data-stu-id="0293b-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0293b-115">说明</span><span class="sxs-lookup"><span data-stu-id="0293b-115">Remarks</span></span>

 <span data-ttu-id="0293b-116">**PROP_ACCT_USER_EMAIL_ADDR**不应在每个帐户上都存在。</span><span class="sxs-lookup"><span data-stu-id="0293b-116">**PROP_ACCT_USER_EMAIL_ADDR** is not expected to exist on every account.</span></span> <span data-ttu-id="0293b-117">例如, Exchange 帐户可以具有[PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) , 而不是**PROP_ACCT_USER_EMAIL_ADDR**, 而对于 SMTP/POP3 帐户, 则会还原该情况。</span><span class="sxs-lookup"><span data-stu-id="0293b-117">For example, an Exchange account could have [PROP_MAPI_IDENTITY_ENTRYID](prop_mapi_identity_entryid.md) but not **PROP_ACCT_USER_EMAIL_ADDR**, while for an SMTP/POP3 account, the situation is reversed.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0293b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0293b-118">See also</span></span>

- [<span data-ttu-id="0293b-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="0293b-119">About the Account Management API</span></span>](about-the-account-management-api.md)

