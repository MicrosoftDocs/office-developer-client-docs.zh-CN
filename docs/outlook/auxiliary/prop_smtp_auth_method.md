---
title: PROP_SMTP_AUTH_METHOD
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 4202cafc-9011-406d-90b3-8dabf531c90b
description: 指定要使用的 SMTP 帐户的身份验证方法。
ms.openlocfilehash: 0c52f1eeca8f7ac3e63cccf712dd672c2247be6a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774452"
---
# <a name="propsmtpauthmethod"></a><span data-ttu-id="92671-103">PROP_SMTP_AUTH_METHOD</span><span class="sxs-lookup"><span data-stu-id="92671-103">PROP_SMTP_AUTH_METHOD</span></span>

<span data-ttu-id="92671-104">指定要使用的 SMTP 帐户的身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="92671-104">Specifies the authentication method to use for the SMTP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="92671-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="92671-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="92671-106">标识符：</span><span class="sxs-lookup"><span data-stu-id="92671-106">Identifier:</span></span>  <br/> |<span data-ttu-id="92671-107">0x0208</span><span class="sxs-lookup"><span data-stu-id="92671-107">0x0208</span></span>  <br/> |
|<span data-ttu-id="92671-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="92671-108">Property type:</span></span>  <br/> |<span data-ttu-id="92671-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="92671-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="92671-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="92671-110">Property tag:</span></span>  <br/> |<span data-ttu-id="92671-111">0x02080003</span><span class="sxs-lookup"><span data-stu-id="92671-111">0x02080003</span></span>  <br/> |
|<span data-ttu-id="92671-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="92671-112">Access:</span></span>  <br/> |<span data-ttu-id="92671-113">只读</span><span class="sxs-lookup"><span data-stu-id="92671-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92671-114">说明</span><span class="sxs-lookup"><span data-stu-id="92671-114">Remarks</span></span>

<span data-ttu-id="92671-115">值是以下常量的位掩码。</span><span class="sxs-lookup"><span data-stu-id="92671-115">The value is a bitmask of the following constants.</span></span> <span data-ttu-id="92671-116">其值，请参阅[常量 （帐户管理 API）](constants-account-management-api.md) 。</span><span class="sxs-lookup"><span data-stu-id="92671-116">See [Constants (Account management API)](constants-account-management-api.md) for their values.</span></span> 
  
- <span data-ttu-id="92671-117">**SMTP_AUTH_SAME_AS_POP**意味着与传入邮件服务器，使用相同的凭据[PROP_INET_USER](prop_inet_user.md)和[PROP_INET_PASSWORD](prop_inet_password.md)提供的。</span><span class="sxs-lookup"><span data-stu-id="92671-117">**SMTP_AUTH_SAME_AS_POP** means using the same credentials as my incoming mail server, as provided by [PROP_INET_USER](prop_inet_user.md) and [PROP_INET_PASSWORD](prop_inet_password.md).</span></span>
    
- <span data-ttu-id="92671-118">**SMTP_AUTH_USER_PASS**是指使用[PROP_SMTP_USER](prop_smtp_user.md)和[PROP_SMTP_PASSWORD](prop_smtp_password.md)所提供的凭据。</span><span class="sxs-lookup"><span data-stu-id="92671-118">**SMTP_AUTH_USER_PASS** means using the credentials as provided by [PROP_SMTP_USER](prop_smtp_user.md) and [PROP_SMTP_PASSWORD](prop_smtp_password.md).</span></span>
    
- <span data-ttu-id="92671-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND**表示请求的用户发送邮件前登录到的传入邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="92671-119">**SMTP_AUTH_RECEIVE_BEFORE_SEND** means requesting the user to log on to the incoming mail server before sending mail.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="92671-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92671-120">See also</span></span>

- [<span data-ttu-id="92671-121">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="92671-121">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)  
- [<span data-ttu-id="92671-122">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="92671-122">Constants (Account management API)</span></span>](constants-account-management-api.md)

