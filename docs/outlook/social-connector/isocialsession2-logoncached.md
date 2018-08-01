---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 登录到社交网络站点使用缓存的凭据。
ms.openlocfilehash: 098ccd2cd3a55affed683886ce1e297ed725475b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779248"
---
# <a name="isocialsession2logoncached"></a><span data-ttu-id="6b96f-103">ISocialSession2::LogonCached</span><span class="sxs-lookup"><span data-stu-id="6b96f-103">ISocialSession2::LogonCached</span></span>

<span data-ttu-id="6b96f-104">登录到社交网络站点使用缓存的凭据。</span><span class="sxs-lookup"><span data-stu-id="6b96f-104">Logs on to the social network site by using cached credentials.</span></span>
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a><span data-ttu-id="6b96f-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b96f-105">Parameters</span></span>

<span data-ttu-id="6b96f-106">_connectIn_</span><span class="sxs-lookup"><span data-stu-id="6b96f-106">_connectIn_</span></span>
  
> <span data-ttu-id="6b96f-107">[in]一个字符串，可以为空或包含的登录凭据，具体取决于在其中 OSC 调用**LogonCached**的上下文。</span><span class="sxs-lookup"><span data-stu-id="6b96f-107">[in] A string that can be empty or contains the logon credentials, depending on the context in which the OSC is calling **LogonCached**.</span></span>
    
<span data-ttu-id="6b96f-108">_userName_</span><span class="sxs-lookup"><span data-stu-id="6b96f-108">_userName_</span></span>
  
> <span data-ttu-id="6b96f-109">[in]一个字符串，包含用户的名称。</span><span class="sxs-lookup"><span data-stu-id="6b96f-109">[in] A string that contains the user name.</span></span>
    
<span data-ttu-id="6b96f-110">_密码_</span><span class="sxs-lookup"><span data-stu-id="6b96f-110">_password_</span></span>
  
> <span data-ttu-id="6b96f-111">[in]一个字符串，包含用户的密码。</span><span class="sxs-lookup"><span data-stu-id="6b96f-111">[in] A string that contains the user's password.</span></span>
    
<span data-ttu-id="6b96f-112">_connectOut_</span><span class="sxs-lookup"><span data-stu-id="6b96f-112">_connectOut_</span></span>
  
> <span data-ttu-id="6b96f-113">[输出]不透明字符串，其中包含凭据。</span><span class="sxs-lookup"><span data-stu-id="6b96f-113">[out] An opaque string that contains credentials.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6b96f-114">说明</span><span class="sxs-lookup"><span data-stu-id="6b96f-114">Remarks</span></span>

<span data-ttu-id="6b96f-115">只有当**useLogonCached**设置为**true**的**功能**返回[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)XML 中，将身份验证调用此方法。</span><span class="sxs-lookup"><span data-stu-id="6b96f-115">This method is called for authentication only if **useLogonCached** is set as **true** in the **capabilities** XML returned by [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md).</span></span>
  
<span data-ttu-id="6b96f-116">Outlook Social Connector (OSC) 调用**LogonCached**，并传递空字符串作为_connectIn_和非空_用户名_和_密码_字符串。</span><span class="sxs-lookup"><span data-stu-id="6b96f-116">The Outlook Social Connector (OSC) calls **LogonCached**, and passes an empty string for  _connectIn_ and non-empty  _userName_ and  _password_ strings.</span></span> <span data-ttu-id="6b96f-117">提供程序使用_用户名_和_密码_登录到社交网络，并返回不透明_connectOut_参数为 OSC 身份验证成功。</span><span class="sxs-lookup"><span data-stu-id="6b96f-117">The provider uses  _userName_ and  _password_ to log on to the social network, and returns an opaque  _connectOut_ parameter to the OSC if authentication succeeds.</span></span> <span data-ttu-id="6b96f-118">如果身份验证失败，提供程序将返回到 OSC OSC_E_LOGON_FAILURE 错误。</span><span class="sxs-lookup"><span data-stu-id="6b96f-118">If authentication fails, the provider returns the OSC_E_LOGON_FAILURE error to the OSC.</span></span> 
  
<span data-ttu-id="6b96f-119">_ConnectOut_参数 OSC，不透明字符串并且通过传递给_connectIn_参数在以后尝试登录到社交网络 OSC。</span><span class="sxs-lookup"><span data-stu-id="6b96f-119">The  _connectOut_ parameter is an opaque string to the OSC, and is passed to the  _connectIn_ parameter on subsequent attempts by the OSC to log on to the social network.</span></span> <span data-ttu-id="6b96f-120">提供程序应该将提供程序希望 OSC 跨连接存储在_connectOut_字符串中的任何凭据。</span><span class="sxs-lookup"><span data-stu-id="6b96f-120">The provider should place any credentials in the  _connectOut_ string that the provider wants the OSC to store across connections.</span></span> <span data-ttu-id="6b96f-121">OSC 不解释_connectOut_中的字符串，并将其存储在 Windows 注册表中之前加密出于安全目的的字符串。</span><span class="sxs-lookup"><span data-stu-id="6b96f-121">The OSC does not interpret the string in  _connectOut_, and encrypts the string for security purposes before storing it in the Windows registry.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6b96f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b96f-122">See also</span></span>

- [<span data-ttu-id="6b96f-123">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6b96f-123">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)

