---
title: PROP_SMTP_SECURE_CONNECTION
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e316a424-d789-4ce5-bcc6-263049f3659e
description: 指定的加密连接使用的 SMTP 帐户的类型。
ms.openlocfilehash: e1c8c8dacf953407d4cbb114aa5ee0a4cdb6acf5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774448"
---
# <a name="propsmtpsecureconnection"></a><span data-ttu-id="9f332-103">PROP_SMTP_SECURE_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="9f332-103">PROP_SMTP_SECURE_CONNECTION</span></span>

<span data-ttu-id="9f332-104">指定的加密连接使用的 SMTP 帐户的类型。</span><span class="sxs-lookup"><span data-stu-id="9f332-104">Specifies the type of encrypted connection to use for an SMTP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="9f332-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="9f332-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9f332-106">标识符：</span><span class="sxs-lookup"><span data-stu-id="9f332-106">Identifier:</span></span>  <br/> |<span data-ttu-id="9f332-107">0x020A</span><span class="sxs-lookup"><span data-stu-id="9f332-107">0x020A</span></span>  <br/> |
|<span data-ttu-id="9f332-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="9f332-108">Property type:</span></span>  <br/> |<span data-ttu-id="9f332-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="9f332-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="9f332-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="9f332-110">Property tag:</span></span>  <br/> |<span data-ttu-id="9f332-111">0x020A0003</span><span class="sxs-lookup"><span data-stu-id="9f332-111">0x020A0003</span></span>  <br/> |
|<span data-ttu-id="9f332-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="9f332-112">Access:</span></span>  <br/> |<span data-ttu-id="9f332-113">只读</span><span class="sxs-lookup"><span data-stu-id="9f332-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f332-114">说明</span><span class="sxs-lookup"><span data-stu-id="9f332-114">Remarks</span></span>

<span data-ttu-id="9f332-115">值可以是以下常量之一。</span><span class="sxs-lookup"><span data-stu-id="9f332-115">The value can be one of the following constants.</span></span> <span data-ttu-id="9f332-116">其值，请参阅[常量 （帐户管理 API）](constants-account-management-api.md) 。</span><span class="sxs-lookup"><span data-stu-id="9f332-116">See [Constants (Account management API)](constants-account-management-api.md) for their values.</span></span> 
  
|<span data-ttu-id="9f332-117">**常量**</span><span class="sxs-lookup"><span data-stu-id="9f332-117">**Constants**</span></span>|<span data-ttu-id="9f332-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="9f332-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f332-119">**ENCRYPT_CONN_NO_SECURITY**</span><span class="sxs-lookup"><span data-stu-id="9f332-119">**ENCRYPT_CONN_NO_SECURITY**</span></span> <br/> |<span data-ttu-id="9f332-120">不使用任何加密。</span><span class="sxs-lookup"><span data-stu-id="9f332-120">Do not use any encryption.</span></span>  <br/> |
|<span data-ttu-id="9f332-121">**ENCRYPT_CONN_SSL**</span><span class="sxs-lookup"><span data-stu-id="9f332-121">**ENCRYPT_CONN_SSL**</span></span> <br/> |<span data-ttu-id="9f332-122">使用安全套接字层 (SSL) 加密。</span><span class="sxs-lookup"><span data-stu-id="9f332-122">Use Secure Socket Layer (SSL) encryption.</span></span>  <br/> |
|<span data-ttu-id="9f332-123">**ENCRYPT_CONN_TLS**</span><span class="sxs-lookup"><span data-stu-id="9f332-123">**ENCRYPT_CONN_TLS**</span></span> <br/> |<span data-ttu-id="9f332-124">使用传输层安全性 (TLS) 加密和身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="9f332-124">Use Transport Layer Security (TLS) encryption and authentication protocol.</span></span>  <br/> |
|<span data-ttu-id="9f332-125">**ENCRYPT_CONN_AUTO**</span><span class="sxs-lookup"><span data-stu-id="9f332-125">**ENCRYPT_CONN_AUTO**</span></span> <br/> |<span data-ttu-id="9f332-126">自动检测并使用支持的邮件服务器的加密方法。</span><span class="sxs-lookup"><span data-stu-id="9f332-126">Automatically detect and use the encryption method supported by the mail server.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9f332-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f332-127">See also</span></span>

- [<span data-ttu-id="9f332-128">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="9f332-128">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md) 
- [<span data-ttu-id="9f332-129">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="9f332-129">Constants (Account management API)</span></span>](constants-account-management-api.md)

