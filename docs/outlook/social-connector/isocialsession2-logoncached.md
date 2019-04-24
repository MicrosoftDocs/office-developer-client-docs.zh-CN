---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 使用缓存凭据登录到社交网络网站。
ms.openlocfilehash: b79c692c01022dd10ecb8d4085f0aedb28a810c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336503"
---
# <a name="isocialsession2logoncached"></a><span data-ttu-id="74856-103">ISocialSession2::LogonCached</span><span class="sxs-lookup"><span data-stu-id="74856-103">ISocialSession2::LogonCached</span></span>

<span data-ttu-id="74856-104">使用缓存凭据登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="74856-104">Logs on to the social network site by using cached credentials.</span></span>
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a><span data-ttu-id="74856-105">参数</span><span class="sxs-lookup"><span data-stu-id="74856-105">Parameters</span></span>

<span data-ttu-id="74856-106">_connectIn_</span><span class="sxs-lookup"><span data-stu-id="74856-106">_connectIn_</span></span>
  
> <span data-ttu-id="74856-107">实时一个字符串, 可以为空或包含登录凭据, 具体取决于 .osc 调用**LogonCached**的上下文。</span><span class="sxs-lookup"><span data-stu-id="74856-107">[in] A string that can be empty or contains the logon credentials, depending on the context in which the OSC is calling **LogonCached**.</span></span>
    
<span data-ttu-id="74856-108">_userName_</span><span class="sxs-lookup"><span data-stu-id="74856-108">_userName_</span></span>
  
> <span data-ttu-id="74856-109">实时一个包含用户名的字符串。</span><span class="sxs-lookup"><span data-stu-id="74856-109">[in] A string that contains the user name.</span></span>
    
<span data-ttu-id="74856-110">_口令_</span><span class="sxs-lookup"><span data-stu-id="74856-110">_password_</span></span>
  
> <span data-ttu-id="74856-111">实时一个包含用户密码的字符串。</span><span class="sxs-lookup"><span data-stu-id="74856-111">[in] A string that contains the user's password.</span></span>
    
<span data-ttu-id="74856-112">_connectOut_</span><span class="sxs-lookup"><span data-stu-id="74856-112">_connectOut_</span></span>
  
> <span data-ttu-id="74856-113">排除包含凭据的不透明字符串。</span><span class="sxs-lookup"><span data-stu-id="74856-113">[out] An opaque string that contains credentials.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="74856-114">注解</span><span class="sxs-lookup"><span data-stu-id="74856-114">Remarks</span></span>

<span data-ttu-id="74856-115">仅当[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)返回的**功能**XML 中的**useLogonCached**设置为**true**时, 才会调用此方法进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74856-115">This method is called for authentication only if **useLogonCached** is set as **true** in the **capabilities** XML returned by [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md).</span></span>
  
<span data-ttu-id="74856-116">Outlook Social Connector (.osc) 调用**LogonCached**, 并为_connectIn_和非空_用户名_和_密码_字符串传递一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="74856-116">The Outlook Social Connector (OSC) calls **LogonCached**, and passes an empty string for  _connectIn_ and non-empty  _userName_ and  _password_ strings.</span></span> <span data-ttu-id="74856-117">提供程序使用_用户名_和_密码_登录到社交网络, 如果身份验证成功, 则向 .osc 返回一个不透明的_connectOut_参数。</span><span class="sxs-lookup"><span data-stu-id="74856-117">The provider uses  _userName_ and  _password_ to log on to the social network, and returns an opaque  _connectOut_ parameter to the OSC if authentication succeeds.</span></span> <span data-ttu-id="74856-118">如果身份验证失败, 则提供程序将向 .osc 返回 OSC_E_LOGON_FAILURE 错误。</span><span class="sxs-lookup"><span data-stu-id="74856-118">If authentication fails, the provider returns the OSC_E_LOGON_FAILURE error to the OSC.</span></span> 
  
<span data-ttu-id="74856-119">_connectOut_参数是一个对 .osc 的不透明字符串, 并在由 .osc 登录社交网络的后续尝试中传递给_connectIn_参数。</span><span class="sxs-lookup"><span data-stu-id="74856-119">The  _connectOut_ parameter is an opaque string to the OSC, and is passed to the  _connectIn_ parameter on subsequent attempts by the OSC to log on to the social network.</span></span> <span data-ttu-id="74856-120">提供程序应将任何凭据放在_connectOut_字符串中, 提供程序希望您的 .osc 在各连接之间存储。</span><span class="sxs-lookup"><span data-stu-id="74856-120">The provider should place any credentials in the  _connectOut_ string that the provider wants the OSC to store across connections.</span></span> <span data-ttu-id="74856-121">.osc 不会解释_connectOut_中的字符串, 在将其存储在 Windows 注册表中之前, 出于安全目的对字符串进行加密。</span><span class="sxs-lookup"><span data-stu-id="74856-121">The OSC does not interpret the string in  _connectOut_, and encrypts the string for security purposes before storing it in the Windows registry.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74856-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74856-122">See also</span></span>

- [<span data-ttu-id="74856-123">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="74856-123">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)

