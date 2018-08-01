---
title: ISocialSessionLogonWeb
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f4217030-5fd1-4ec4-a83f-752717fbb787
description: 登录到使用基于表单的身份验证的社交网络站点。
ms.openlocfilehash: 4af0301d5b619ce7f9ff54b97f54b4b00408a564
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779241"
---
# <a name="isocialsessionlogonweb"></a><span data-ttu-id="e1b8c-103">ISocialSession::LogonWeb</span><span class="sxs-lookup"><span data-stu-id="e1b8c-103">ISocialSession::LogonWeb</span></span>

<span data-ttu-id="e1b8c-104">登录到使用基于表单的身份验证的社交网络站点。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-104">Logs on to the social network site by using forms-based authentication.</span></span>
  
```cpp
HRESULT _stdcall LogonWeb([in] BSTR connectIn, [out] BSTR* connectOut);
```

## <a name="parameters"></a><span data-ttu-id="e1b8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1b8c-105">Parameters</span></span>

<span data-ttu-id="e1b8c-106">_connectIn_</span><span class="sxs-lookup"><span data-stu-id="e1b8c-106">_connectIn_</span></span>
  
> <span data-ttu-id="e1b8c-107">[in]一个字符串，为**null**，向 web 或一个包含登录凭据，具体取决于在登录过程时调用此方法的上下文字符串上登录表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-107">[in] A string that is **null**, an URL to a logon form on the web, or a string that contains logon credentials, depending on the context in the logon process when this method is called.</span></span>
    
<span data-ttu-id="e1b8c-108">_connectOut_</span><span class="sxs-lookup"><span data-stu-id="e1b8c-108">_connectOut_</span></span>
  
> <span data-ttu-id="e1b8c-109">[输出]一个字符串，包含登录凭据。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-109">[out] A string that contains logon credentials.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1b8c-110">说明</span><span class="sxs-lookup"><span data-stu-id="e1b8c-110">Remarks</span></span>

<span data-ttu-id="e1b8c-111">Outlook Social Connector (OSC) 提供程序指示它支持基于表单的身份验证时，才调用**LogonWeb**方法。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-111">The Outlook Social Connector (OSC) calls the **LogonWeb** method only if the provider indicates that it supports forms-based authentication.</span></span> <span data-ttu-id="e1b8c-112">提供程序指示它通过设置为**true** **功能**的 XML **useLogonWebAuth**需要基于表单的身份验证。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-112">The provider indicates that it requires forms-based authentication by setting **useLogonWebAuth** as **true** in the XML for **capabilities**.</span></span> <span data-ttu-id="e1b8c-113">如果提供程序将**useLogonWebAuth**设置为**false**，则 OSC 使用基本身份验证，并调用[ISocialSession::Logon](isocialsession-logon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-113">If the provider sets **useLogonWebAuth** as **false**, the OSC uses basic authentication and calls the [ISocialSession::Logon](isocialsession-logon.md) method.</span></span> 
  
<span data-ttu-id="e1b8c-114">登录到社交网络站点使用基于表单的身份验证涉及的特定顺序调用**LogonWeb**和[ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md)方法：</span><span class="sxs-lookup"><span data-stu-id="e1b8c-114">Logging on to a social network site by using forms-based authentication involves calling the **LogonWeb** and [ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md) methods in a specific order:</span></span> 
  
1. <span data-ttu-id="e1b8c-115">OSC 调用**LogonWeb**首次给_connectIn_参数传递**null** 。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-115">The OSC calls **LogonWeb** the first time, passing **null** to the  _connectIn_ parameter.</span></span> 
    
2. <span data-ttu-id="e1b8c-116">提供程序将引发到 OSC OSC_E_AUTH_ERROR 错误。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-116">The provider raises the OSC_E_AUTH_ERROR error to the OSC.</span></span>
    
3. <span data-ttu-id="e1b8c-117">OSC 接下来将调用**GetLogonUrl**。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-117">The OSC next calls **GetLogonUrl**.</span></span>
    
4. <span data-ttu-id="e1b8c-118">提供程序返回**GetLogonUrl**方法中的登录页面的相应 URL。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-118">The provider returns the appropriate URL to a logon page in the **GetLogonUrl** method.</span></span> 
    
5. <span data-ttu-id="e1b8c-119">OSC 使用**GetLogonUrl**返回的 URL 来显示基于表单的登录页。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-119">The OSC uses the URL returned by **GetLogonUrl** to display the forms-based logon page.</span></span> 
    
6. <span data-ttu-id="e1b8c-120">OSC 然后调用**LogonWeb**第二次，将 URL 传递给_connectIn_参数中的登录窗体。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-120">The OSC then calls **LogonWeb** a second time, passing the URL to the logon form in the  _connectIn_ parameter.</span></span> 
    
7. <span data-ttu-id="e1b8c-121">如果身份验证成功，提供程序返回_connectOut_参数中具有到 OSC 登录凭据。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-121">If authentication succeeds, the provider returns logon credentials in the  _connectOut_ parameter to the OSC.</span></span> <span data-ttu-id="e1b8c-122">如果身份验证失败，提供程序将引发到 OSC OSC_E_AUTH_ERROR 错误。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-122">If authentication fails, the provider raises the OSC_E_AUTH_ERROR error to the OSC.</span></span> 
    
<span data-ttu-id="e1b8c-123">如果 OSC 提供程序支持使用缓存的凭据登录，它指定**useLogonCached**为**true**的**功能**XML 中。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-123">If the OSC provider supports logging on using cached credentials, it specifies **useLogonCached** as **true** in the **capabilities** XML.</span></span> <span data-ttu-id="e1b8c-124">提供程序应该将提供程序希望 OSC 跨连接存储在_connectOut_字符串中的任何登录凭据。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-124">The provider should place any logon credentials in the  _connectOut_ string that the provider wants the OSC to store across connections.</span></span> <span data-ttu-id="e1b8c-125">OSC 不解释_connectOut_字符串。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-125">The OSC does not interpret the  _connectOut_ string.</span></span> <span data-ttu-id="e1b8c-126">OSC 验证该**useLogonCached**为**true**后，OSC 将其存储在 Windows 注册表之前对加密的安全的字符串。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-126">After the OSC verifies that **useLogonCached** is **true**, the OSC encrypts the string for security before storing it in the Windows registry.</span></span> <span data-ttu-id="e1b8c-127">OSC 将_connectIn_参数传递到此字符串上调用[ISocialSession2::LogonCached](isocialsession2-logoncached.md)登录到社交网络上的后续尝试。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-127">The OSC passes this string to the  _connectIn_ parameter on subsequent attempts to log on to the social network by calling [ISocialSession2::LogonCached](isocialsession2-logoncached.md).</span></span> 
  
<span data-ttu-id="e1b8c-128">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b8c-128">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1b8c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1b8c-129">See also</span></span>

- [<span data-ttu-id="e1b8c-130">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e1b8c-130">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)
- [<span data-ttu-id="e1b8c-131">基于表单的身份验证</span><span class="sxs-lookup"><span data-stu-id="e1b8c-131">Forms-Based Authentication</span></span>](forms-based-authentication.md)

