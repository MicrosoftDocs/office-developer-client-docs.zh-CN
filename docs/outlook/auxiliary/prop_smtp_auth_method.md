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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434639"
---
# <a name="prop_smtp_auth_method"></a><span data-ttu-id="619a5-103">PROP_SMTP_AUTH_METHOD</span><span class="sxs-lookup"><span data-stu-id="619a5-103">PROP_SMTP_AUTH_METHOD</span></span>

<span data-ttu-id="619a5-104">指定要用于 SMTP 帐户的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="619a5-104">Specifies the authentication method to use for the SMTP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="619a5-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="619a5-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="619a5-106">标识符:</span><span class="sxs-lookup"><span data-stu-id="619a5-106">Identifier:</span></span>  <br/> |<span data-ttu-id="619a5-107">0x0208</span><span class="sxs-lookup"><span data-stu-id="619a5-107">0x0208</span></span>  <br/> |
|<span data-ttu-id="619a5-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="619a5-108">Property type:</span></span>  <br/> |<span data-ttu-id="619a5-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="619a5-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="619a5-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="619a5-110">Property tag:</span></span>  <br/> |<span data-ttu-id="619a5-111">0x02080003</span><span class="sxs-lookup"><span data-stu-id="619a5-111">0x02080003</span></span>  <br/> |
|<span data-ttu-id="619a5-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="619a5-112">Access:</span></span>  <br/> |<span data-ttu-id="619a5-113">只读</span><span class="sxs-lookup"><span data-stu-id="619a5-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="619a5-114">备注</span><span class="sxs-lookup"><span data-stu-id="619a5-114">Remarks</span></span>

<span data-ttu-id="619a5-115">该值是以下常量的位掩码。</span><span class="sxs-lookup"><span data-stu-id="619a5-115">The value is a bitmask of the following constants.</span></span> <span data-ttu-id="619a5-116">请参阅 [Constants (Account management API) ](constants-account-management-api.md) 了解其值。</span><span class="sxs-lookup"><span data-stu-id="619a5-116">See [Constants (Account management API)](constants-account-management-api.md) for their values.</span></span> 
  
- <span data-ttu-id="619a5-117">**SMTP_AUTH_SAME_AS_POP** 使用与传入邮件服务器相同的凭据，如 PROP_INET_USER [和](prop_inet_user.md)[PROP_INET_PASSWORD 提供](prop_inet_password.md)。</span><span class="sxs-lookup"><span data-stu-id="619a5-117">**SMTP_AUTH_SAME_AS_POP** means using the same credentials as my incoming mail server, as provided by [PROP_INET_USER](prop_inet_user.md) and [PROP_INET_PASSWORD](prop_inet_password.md).</span></span>
    
- <span data-ttu-id="619a5-118">**SMTP_AUTH_USER_PASS** 表示使用由 PROP_SMTP_USER 和 [PROP_SMTP_PASSWORD](prop_smtp_user.md) [提供的凭据](prop_smtp_password.md)。</span><span class="sxs-lookup"><span data-stu-id="619a5-118">**SMTP_AUTH_USER_PASS** means using the credentials as provided by [PROP_SMTP_USER](prop_smtp_user.md) and [PROP_SMTP_PASSWORD](prop_smtp_password.md).</span></span>
    
- <span data-ttu-id="619a5-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND** 请求用户在发送邮件之前登录传入邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="619a5-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND** means requesting the user to log on to the incoming mail server before sending mail.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="619a5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="619a5-120">See also</span></span>

- [<span data-ttu-id="619a5-121">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="619a5-121">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)  
- [<span data-ttu-id="619a5-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="619a5-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

