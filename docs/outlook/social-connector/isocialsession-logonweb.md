---
title: ISocialSessionLogonWeb
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f4217030-5fd1-4ec4-a83f-752717fbb787
description: 使用基于表单的身份验证登录到社交网络网站。
ms.openlocfilehash: 7ef7af8c1c2cdb783bdecd71b29635468e19dc6a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430334"
---
# <a name="isocialsessionlogonweb"></a><span data-ttu-id="4939c-103">ISocialSession::LogonWeb</span><span class="sxs-lookup"><span data-stu-id="4939c-103">ISocialSession::LogonWeb</span></span>

<span data-ttu-id="4939c-104">使用基于表单的身份验证登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="4939c-104">Logs on to the social network site by using forms-based authentication.</span></span>
  
```cpp
HRESULT _stdcall LogonWeb([in] BSTR connectIn, [out] BSTR* connectOut);
```

## <a name="parameters"></a><span data-ttu-id="4939c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4939c-105">Parameters</span></span>

<span data-ttu-id="4939c-106">_connectIn_</span><span class="sxs-lookup"><span data-stu-id="4939c-106">_connectIn_</span></span>
  
> <span data-ttu-id="4939c-107">[in]一个 **为空** 的字符串、Web 上登录表单的 URL 或包含登录凭据的字符串，具体取决于调用此方法时登录进程中的上下文。</span><span class="sxs-lookup"><span data-stu-id="4939c-107">[in] A string that is **null**, an URL to a logon form on the web, or a string that contains logon credentials, depending on the context in the logon process when this method is called.</span></span>
    
<span data-ttu-id="4939c-108">_connectOut_</span><span class="sxs-lookup"><span data-stu-id="4939c-108">_connectOut_</span></span>
  
> <span data-ttu-id="4939c-109">[out]包含登录凭据的字符串。</span><span class="sxs-lookup"><span data-stu-id="4939c-109">[out] A string that contains logon credentials.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4939c-110">备注</span><span class="sxs-lookup"><span data-stu-id="4939c-110">Remarks</span></span>

<span data-ttu-id="4939c-111">OSC Outlook连接器 (OSC) 仅在提供程序指示其支持基于表单的身份验证时调用 **LogonWeb** 方法。</span><span class="sxs-lookup"><span data-stu-id="4939c-111">The Outlook Social Connector (OSC) calls the **LogonWeb** method only if the provider indicates that it supports forms-based authentication.</span></span> <span data-ttu-id="4939c-112">提供程序通过针对功能在 XML 中将 **useLogonWebAuth** 设置为 **true** 来指示它需要基于表单 **的身份验证**。</span><span class="sxs-lookup"><span data-stu-id="4939c-112">The provider indicates that it requires forms-based authentication by setting **useLogonWebAuth** as **true** in the XML for **capabilities**.</span></span> <span data-ttu-id="4939c-113">如果提供程序将 **useLogonWebAuth** 设置为 **false，** 则 OSC 将使用基本身份验证并调用 [ISocialSession：：Logon](isocialsession-logon.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="4939c-113">If the provider sets **useLogonWebAuth** as **false**, the OSC uses basic authentication and calls the [ISocialSession::Logon](isocialsession-logon.md) method.</span></span> 
  
<span data-ttu-id="4939c-114">使用基于表单的身份验证登录到社交网络网站涉及按特定顺序调用 **LogonWeb** 和 [ISocialSession：：GetLogonUrl](isocialsession-getlogonurl.md) 方法：</span><span class="sxs-lookup"><span data-stu-id="4939c-114">Logging on to a social network site by using forms-based authentication involves calling the **LogonWeb** and [ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md) methods in a specific order:</span></span> 
  
1. <span data-ttu-id="4939c-115">OSC 第一 **次调用 LogonWeb，** 将 **null** 传递给  _connectIn_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4939c-115">The OSC calls **LogonWeb** the first time, passing **null** to the  _connectIn_ parameter.</span></span> 
    
2. <span data-ttu-id="4939c-116">提供程序向 OSC OSC_E_AUTH_ERROR错误。</span><span class="sxs-lookup"><span data-stu-id="4939c-116">The provider raises the OSC_E_AUTH_ERROR error to the OSC.</span></span>
    
3. <span data-ttu-id="4939c-117">OSC 接下来调用 **GetLogonUrl**。</span><span class="sxs-lookup"><span data-stu-id="4939c-117">The OSC next calls **GetLogonUrl**.</span></span>
    
4. <span data-ttu-id="4939c-118">提供程序将相应的 URL 返回到 **GetLogonUrl** 方法中的登录页。</span><span class="sxs-lookup"><span data-stu-id="4939c-118">The provider returns the appropriate URL to a logon page in the **GetLogonUrl** method.</span></span> 
    
5. <span data-ttu-id="4939c-119">OSC 使用 **GetLogonUrl** 返回的 URL 显示基于表单的登录页。</span><span class="sxs-lookup"><span data-stu-id="4939c-119">The OSC uses the URL returned by **GetLogonUrl** to display the forms-based logon page.</span></span> 
    
6. <span data-ttu-id="4939c-120">然后，OSC 再次调用 **LogonWeb，** 将 URL 传递到  _connectIn_ 参数中的登录表单。</span><span class="sxs-lookup"><span data-stu-id="4939c-120">The OSC then calls **LogonWeb** a second time, passing the URL to the logon form in the  _connectIn_ parameter.</span></span> 
    
7. <span data-ttu-id="4939c-121">如果身份验证成功，提供程序会向 OSC 返回  _connectOut_ 参数中的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="4939c-121">If authentication succeeds, the provider returns logon credentials in the  _connectOut_ parameter to the OSC.</span></span> <span data-ttu-id="4939c-122">如果身份验证失败，提供程序会向 OSC OSC_E_AUTH_ERROR错误。</span><span class="sxs-lookup"><span data-stu-id="4939c-122">If authentication fails, the provider raises the OSC_E_AUTH_ERROR error to the OSC.</span></span> 
    
<span data-ttu-id="4939c-123">如果 OSC 提供程序支持使用缓存凭据登录，则它会在功能 **XML** 中将 **useLogonCached** 指定为 **true。**</span><span class="sxs-lookup"><span data-stu-id="4939c-123">If the OSC provider supports logging on using cached credentials, it specifies **useLogonCached** as **true** in the **capabilities** XML.</span></span> <span data-ttu-id="4939c-124">提供程序应该将任何登录凭据放在提供程序希望 OSC 跨连接存储的  _connectOut_ 字符串中。</span><span class="sxs-lookup"><span data-stu-id="4939c-124">The provider should place any logon credentials in the  _connectOut_ string that the provider wants the OSC to store across connections.</span></span> <span data-ttu-id="4939c-125">OSC 不会解释  _connectOut_ 字符串。</span><span class="sxs-lookup"><span data-stu-id="4939c-125">The OSC does not interpret the  _connectOut_ string.</span></span> <span data-ttu-id="4939c-126">在 OSC 验证 **useLogonCached** 为 **true** 后，OSC 会先对字符串进行加密，然后再将其存储在 Windows注册表中。</span><span class="sxs-lookup"><span data-stu-id="4939c-126">After the OSC verifies that **useLogonCached** is **true**, the OSC encrypts the string for security before storing it in the Windows registry.</span></span> <span data-ttu-id="4939c-127">OSC 在后续尝试通过调用 [ISocialSession2：：LogonCached](isocialsession2-logoncached.md)登录到社交网络时，将此字符串传递给 _connectIn_ 参数。</span><span class="sxs-lookup"><span data-stu-id="4939c-127">The OSC passes this string to the  _connectIn_ parameter on subsequent attempts to log on to the social network by calling [ISocialSession2::LogonCached](isocialsession2-logoncached.md).</span></span> 
  
<span data-ttu-id="4939c-128">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="4939c-128">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4939c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4939c-129">See also</span></span>

- [<span data-ttu-id="4939c-130">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4939c-130">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)
- [<span data-ttu-id="4939c-131">基于表单的身份验证</span><span class="sxs-lookup"><span data-stu-id="4939c-131">Forms-Based Authentication</span></span>](forms-based-authentication.md)

