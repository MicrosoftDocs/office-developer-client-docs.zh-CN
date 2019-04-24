---
title: PROP_SMTP_AUTH_METHOD
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 4202cafc-9011-406d-90b3-8dabf531c90b
description: 指定要用于 SMTP 帐户的身份验证方法。
ms.openlocfilehash: bb5adeb1fe73ed8b7ab69ca584215b44e1a9e4b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326500"
---
# <a name="propsmtpauthmethod"></a><span data-ttu-id="db007-103">PROP_SMTP_AUTH_METHOD</span><span class="sxs-lookup"><span data-stu-id="db007-103">PROP_SMTP_AUTH_METHOD</span></span>

<span data-ttu-id="db007-104">指定要用于 SMTP 帐户的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="db007-104">Specifies the authentication method to use for the SMTP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="db007-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="db007-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="db007-106">标识符:</span><span class="sxs-lookup"><span data-stu-id="db007-106">Identifier:</span></span>  <br/> |<span data-ttu-id="db007-107">0x0208</span><span class="sxs-lookup"><span data-stu-id="db007-107">0x0208</span></span>  <br/> |
|<span data-ttu-id="db007-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="db007-108">Property type:</span></span>  <br/> |<span data-ttu-id="db007-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="db007-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="db007-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="db007-110">Property tag:</span></span>  <br/> |<span data-ttu-id="db007-111">0x02080003</span><span class="sxs-lookup"><span data-stu-id="db007-111">0x02080003</span></span>  <br/> |
|<span data-ttu-id="db007-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="db007-112">Access:</span></span>  <br/> |<span data-ttu-id="db007-113">只读</span><span class="sxs-lookup"><span data-stu-id="db007-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="db007-114">注解</span><span class="sxs-lookup"><span data-stu-id="db007-114">Remarks</span></span>

<span data-ttu-id="db007-115">该值是以下常量的位掩码。</span><span class="sxs-lookup"><span data-stu-id="db007-115">The value is a bitmask of the following constants.</span></span> <span data-ttu-id="db007-116">有关其值, 请参阅[常量 (帐户管理 API)](constants-account-management-api.md) 。</span><span class="sxs-lookup"><span data-stu-id="db007-116">See [Constants (Account management API)](constants-account-management-api.md) for their values.</span></span> 
  
- <span data-ttu-id="db007-117">**SMTP_AUTH_SAME_AS_POP**意味着使用与我的传入邮件服务器相同的凭据, 如[PROP_INET_USER](prop_inet_user.md)和[PROP_INET_PASSWORD](prop_inet_password.md)提供的一样。</span><span class="sxs-lookup"><span data-stu-id="db007-117">**SMTP_AUTH_SAME_AS_POP** means using the same credentials as my incoming mail server, as provided by [PROP_INET_USER](prop_inet_user.md) and [PROP_INET_PASSWORD](prop_inet_password.md).</span></span>
    
- <span data-ttu-id="db007-118">**SMTP_AUTH_USER_PASS**是指使用[PROP_SMTP_USER](prop_smtp_user.md)和[PROP_SMTP_PASSWORD](prop_smtp_password.md)提供的凭据。</span><span class="sxs-lookup"><span data-stu-id="db007-118">**SMTP_AUTH_USER_PASS** means using the credentials as provided by [PROP_SMTP_USER](prop_smtp_user.md) and [PROP_SMTP_PASSWORD](prop_smtp_password.md).</span></span>
    
- <span data-ttu-id="db007-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND**意味着请求用户在发送邮件之前登录到传入邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="db007-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND** means requesting the user to log on to the incoming mail server before sending mail.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="db007-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db007-120">See also</span></span>

- [<span data-ttu-id="db007-121">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="db007-121">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)  
- [<span data-ttu-id="db007-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="db007-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

