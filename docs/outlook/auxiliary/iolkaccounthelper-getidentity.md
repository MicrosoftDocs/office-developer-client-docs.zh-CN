---
title: IOlkAccountHelperGetIdentity
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea8b8f02-959f-cd71-9cfe-5ebdf4bae2bc
description: 获取帐户的配置文件名称。
ms.openlocfilehash: d725f309a29b026395e2795a49d31b45a4a49562
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322104"
---
# <a name="iolkaccounthelpergetidentity"></a><span data-ttu-id="2b41a-103">IOlkAccountHelper::GetIdentity</span><span class="sxs-lookup"><span data-stu-id="2b41a-103">IOlkAccountHelper::GetIdentity</span></span>

<span data-ttu-id="2b41a-104">获取帐户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="2b41a-104">Gets the profile name of an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2b41a-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="2b41a-105">Quick info</span></span>

<span data-ttu-id="2b41a-106">请参阅 [IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="2b41a-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetIdentity (  
    LPWSTR pwszIdentity, 
    DWORD *pcch 
);
```

## <a name="parameters"></a><span data-ttu-id="2b41a-107">参数</span><span class="sxs-lookup"><span data-stu-id="2b41a-107">Parameters</span></span>

<span data-ttu-id="2b41a-108">_pwszIdentity_</span><span class="sxs-lookup"><span data-stu-id="2b41a-108">_pwszIdentity_</span></span>
  
> <span data-ttu-id="2b41a-109">[in][out]配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="2b41a-109">[in][out] The profile name.</span></span>
    
<span data-ttu-id="2b41a-110">_pcch_</span><span class="sxs-lookup"><span data-stu-id="2b41a-110">_pcch_</span></span>
  
> <span data-ttu-id="2b41a-111">[in][out]调用此方法时，包含 ( _pwszIdentity_) 字符数的大小。</span><span class="sxs-lookup"><span data-stu-id="2b41a-111">[in] [out] Upon calling this method, contains the size (in number of characters) of  _pwszIdentity_ that has been allocated.</span></span> <span data-ttu-id="2b41a-112">返回时，包含返回的配置文件名称的实际长度，包括以 0 为终止符的字符。</span><span class="sxs-lookup"><span data-stu-id="2b41a-112">Upon return, contains the actual length, including the 0-terminating character, of the returned profile name.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="2b41a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="2b41a-113">Return values</span></span>

|<span data-ttu-id="2b41a-114">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="2b41a-114">**HRESULT**</span></span>|<span data-ttu-id="2b41a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b41a-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b41a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b41a-116">S_OK</span></span>  <br/> |<span data-ttu-id="2b41a-117">调用成功。</span><span class="sxs-lookup"><span data-stu-id="2b41a-117">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="2b41a-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2b41a-118">E_OUTOFMEMORY</span></span>  <br/> |<span data-ttu-id="2b41a-119">返回的配置文件名称长于  _pwszIdentity 的大小_。</span><span class="sxs-lookup"><span data-stu-id="2b41a-119">The returned profile name is longer than the size of  _pwszIdentity_.</span></span>  <br/> |
|<span data-ttu-id="2b41a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2b41a-120">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="2b41a-121">_pcch_ 为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2b41a-121">_pcch_ is NULL.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2b41a-122">备注</span><span class="sxs-lookup"><span data-stu-id="2b41a-122">Remarks</span></span>

<span data-ttu-id="2b41a-123">如果  _pwszIdentity_ 太小，无法保留配置文件名称，则返回时不会设置该名称  _，pcch_ 将指向  _pwszIdentity 所需的大小_。</span><span class="sxs-lookup"><span data-stu-id="2b41a-123">If  _pwszIdentity_ is too small to hold the profile name, it will not be set on return, and  _pcch_ will point to the size required for  _pwszIdentity_.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2b41a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b41a-124">See also</span></span>

- [<span data-ttu-id="2b41a-125">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="2b41a-125">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="2b41a-126">PidTagProfileName</span><span class="sxs-lookup"><span data-stu-id="2b41a-126">PidTagProfileName</span></span>](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx)

