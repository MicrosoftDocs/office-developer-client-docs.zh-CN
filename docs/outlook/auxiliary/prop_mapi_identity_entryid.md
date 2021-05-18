---
title: PROP_MAPI_IDENTITY_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c64db8ea-d6ad-4fb9-97aa-958e5a0daf8f
description: 检索或设置帐户的通讯簿条目 ID。
ms.openlocfilehash: 2352f64b46e9884e95b7bf1f3693321f7cd224ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326430"
---
# <a name="prop_mapi_identity_entryid"></a><span data-ttu-id="e55f8-103">PROP_MAPI_IDENTITY_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="e55f8-103">PROP_MAPI_IDENTITY_ENTRYID</span></span>

<span data-ttu-id="e55f8-104">检索或设置帐户的通讯簿条目 ID。</span><span class="sxs-lookup"><span data-stu-id="e55f8-104">Retrieves or sets the address book entry ID for the account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e55f8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="e55f8-105">Quick info</span></span>

<span data-ttu-id="e55f8-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="e55f8-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e55f8-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="e55f8-107">Identifier:</span></span>  <br/> |<span data-ttu-id="e55f8-108">0x2002</span><span class="sxs-lookup"><span data-stu-id="e55f8-108">0x2002</span></span>  <br/> |
|<span data-ttu-id="e55f8-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="e55f8-109">Property type:</span></span>  <br/> |<span data-ttu-id="e55f8-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e55f8-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e55f8-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="e55f8-111">Property tag:</span></span>  <br/> |<span data-ttu-id="e55f8-112">0x20020102</span><span class="sxs-lookup"><span data-stu-id="e55f8-112">0x20020102</span></span>  <br/> |
|<span data-ttu-id="e55f8-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="e55f8-113">Access:</span></span>  <br/> |<span data-ttu-id="e55f8-114">读/写</span><span class="sxs-lookup"><span data-stu-id="e55f8-114">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e55f8-115">备注</span><span class="sxs-lookup"><span data-stu-id="e55f8-115">Remarks</span></span>

 <span data-ttu-id="e55f8-116">**PROP \_MAPI \_ IDENTITY \_ ENTRYID** 不应存在于每个帐户上。</span><span class="sxs-lookup"><span data-stu-id="e55f8-116">**PROP\_MAPI\_IDENTITY\_ENTRYID** is not expected to exist on every account.</span></span> <span data-ttu-id="e55f8-117">例如，Exchange 帐户可以设置 **PROP \_ MAPI \_ IDENTITY \_ ENTRYID，** 而不是 [PROP \_ ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md)，而对于 SMTP/POP3 帐户，情况将反转。</span><span class="sxs-lookup"><span data-stu-id="e55f8-117">For example, an Exchange account could have **PROP\_MAPI\_IDENTITY\_ENTRYID** set and not [PROP\_ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md), while for an SMTP/POP3 account the situation is reversed.</span></span> <span data-ttu-id="e55f8-118">**PROP \_MAPI_IDENTITY_ENTRYID** 返回条目 ID，该值类似于 [IMAPISession：：QueryIdentity](https://msdn.microsoft.com/library/a2cdda90-5457-49a7-b98c-7273ffe5cbbc%28Office.15%29.aspx)中的 _lppEntryID_ 返回的值。</span><span class="sxs-lookup"><span data-stu-id="e55f8-118">**PROP\_MAPI_IDENTITY_ENTRYID** returns an entry ID that is similar to the value returned by  _lppEntryID_ in [IMAPISession::QueryIdentity](https://msdn.microsoft.com/library/a2cdda90-5457-49a7-b98c-7273ffe5cbbc%28Office.15%29.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e55f8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e55f8-119">See also</span></span>

- [<span data-ttu-id="e55f8-120">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="e55f8-120">About the Account Management API</span></span>](about-the-account-management-api.md)

