---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 使用缓存的凭据登录到社交网络网站。
ms.openlocfilehash: b79c692c01022dd10ecb8d4085f0aedb28a810c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436620"
---
# <a name="isocialsession2logoncached"></a><span data-ttu-id="29351-103">ISocialSession2::LogonCached</span><span class="sxs-lookup"><span data-stu-id="29351-103">ISocialSession2::LogonCached</span></span>

<span data-ttu-id="29351-104">使用缓存的凭据登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="29351-104">Logs on to the social network site by using cached credentials.</span></span>
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a><span data-ttu-id="29351-105">参数</span><span class="sxs-lookup"><span data-stu-id="29351-105">Parameters</span></span>

<span data-ttu-id="29351-106">_connectIn_</span><span class="sxs-lookup"><span data-stu-id="29351-106">_connectIn_</span></span>
  
> <span data-ttu-id="29351-107">[in]一个可为空或包含登录凭据的字符串，具体取决于 OSC 调用 **LogonCached** 的上下文。</span><span class="sxs-lookup"><span data-stu-id="29351-107">[in] A string that can be empty or contains the logon credentials, depending on the context in which the OSC is calling **LogonCached**.</span></span>
    
<span data-ttu-id="29351-108">_userName_</span><span class="sxs-lookup"><span data-stu-id="29351-108">_userName_</span></span>
  
> <span data-ttu-id="29351-109">[in]包含用户名的字符串。</span><span class="sxs-lookup"><span data-stu-id="29351-109">[in] A string that contains the user name.</span></span>
    
<span data-ttu-id="29351-110">_password_</span><span class="sxs-lookup"><span data-stu-id="29351-110">_password_</span></span>
  
> <span data-ttu-id="29351-111">[in]包含用户密码的字符串。</span><span class="sxs-lookup"><span data-stu-id="29351-111">[in] A string that contains the user's password.</span></span>
    
<span data-ttu-id="29351-112">_connectOut_</span><span class="sxs-lookup"><span data-stu-id="29351-112">_connectOut_</span></span>
  
> <span data-ttu-id="29351-113">[out]包含凭据的不透明字符串。</span><span class="sxs-lookup"><span data-stu-id="29351-113">[out] An opaque string that contains credentials.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="29351-114">备注</span><span class="sxs-lookup"><span data-stu-id="29351-114">Remarks</span></span>

<span data-ttu-id="29351-115">只有在 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)返回的功能 **XML** 中 **useLogonCached** 设置为 **true** 时，才对身份验证调用此方法。</span><span class="sxs-lookup"><span data-stu-id="29351-115">This method is called for authentication only if **useLogonCached** is set as **true** in the **capabilities** XML returned by [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md).</span></span>
  
<span data-ttu-id="29351-116">OSC Outlook Social Connector (调用 **LogonCached**) ，并传递 _connectIn_ 的空字符串和非空 _的 userName_ 和 _密码_ 字符串。</span><span class="sxs-lookup"><span data-stu-id="29351-116">The Outlook Social Connector (OSC) calls **LogonCached**, and passes an empty string for  _connectIn_ and non-empty  _userName_ and  _password_ strings.</span></span> <span data-ttu-id="29351-117">提供程序使用  _userName_ 和  _密码_ 登录社交网络，如果身份验证成功，则向 OSC 返回不透明  _的 connectOut_ 参数。</span><span class="sxs-lookup"><span data-stu-id="29351-117">The provider uses  _userName_ and  _password_ to log on to the social network, and returns an opaque  _connectOut_ parameter to the OSC if authentication succeeds.</span></span> <span data-ttu-id="29351-118">如果身份验证失败，提供程序将OSC_E_LOGON_FAILURE错误返回到 OSC。</span><span class="sxs-lookup"><span data-stu-id="29351-118">If authentication fails, the provider returns the OSC_E_LOGON_FAILURE error to the OSC.</span></span> 
  
<span data-ttu-id="29351-119">_connectOut_ 参数是 OSC 的不透明字符串，在 OSC 随后尝试登录社交网络时将传递给 _connectIn_ 参数。</span><span class="sxs-lookup"><span data-stu-id="29351-119">The  _connectOut_ parameter is an opaque string to the OSC, and is passed to the  _connectIn_ parameter on subsequent attempts by the OSC to log on to the social network.</span></span> <span data-ttu-id="29351-120">提供程序应在  _connectOut_ 字符串中放置提供程序希望 OSC 跨连接存储的任何凭据。</span><span class="sxs-lookup"><span data-stu-id="29351-120">The provider should place any credentials in the  _connectOut_ string that the provider wants the OSC to store across connections.</span></span> <span data-ttu-id="29351-121">OSC 不会在 _connectOut_ 中解释字符串，并出于安全目的对字符串进行加密，然后再将其存储在Windows注册表中。</span><span class="sxs-lookup"><span data-stu-id="29351-121">The OSC does not interpret the string in  _connectOut_, and encrypts the string for security purposes before storing it in the Windows registry.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29351-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29351-122">See also</span></span>

- [<span data-ttu-id="29351-123">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="29351-123">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)

