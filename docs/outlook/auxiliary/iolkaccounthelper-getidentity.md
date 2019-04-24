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
# <a name="iolkaccounthelpergetidentity"></a><span data-ttu-id="75a1c-103">IOlkAccountHelper::GetIdentity</span><span class="sxs-lookup"><span data-stu-id="75a1c-103">IOlkAccountHelper::GetIdentity</span></span>

<span data-ttu-id="75a1c-104">获取帐户的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="75a1c-104">Gets the profile name of an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="75a1c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="75a1c-105">Quick info</span></span>

<span data-ttu-id="75a1c-106">请参阅[IOlkAccountHelper](iolkaccounthelper.md)。</span><span class="sxs-lookup"><span data-stu-id="75a1c-106">See [IOlkAccountHelper](iolkaccounthelper.md).</span></span>
  
```cpp
HRESULT IOlkAccountHelper::GetIdentity (  
    LPWSTR pwszIdentity, 
    DWORD *pcch 
);
```

## <a name="parameters"></a><span data-ttu-id="75a1c-107">参数</span><span class="sxs-lookup"><span data-stu-id="75a1c-107">Parameters</span></span>

<span data-ttu-id="75a1c-108">_pwszIdentity_</span><span class="sxs-lookup"><span data-stu-id="75a1c-108">_pwszIdentity_</span></span>
  
> <span data-ttu-id="75a1c-109">实时排除配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="75a1c-109">[in][out] The profile name.</span></span>
    
<span data-ttu-id="75a1c-110">_pcch_</span><span class="sxs-lookup"><span data-stu-id="75a1c-110">_pcch_</span></span>
  
> <span data-ttu-id="75a1c-111">实时排除调用此方法时, 将包含已分配的_pwszIdentity_的大小 (以字符数为单位)。</span><span class="sxs-lookup"><span data-stu-id="75a1c-111">[in] [out] Upon calling this method, contains the size (in number of characters) of  _pwszIdentity_ that has been allocated.</span></span> <span data-ttu-id="75a1c-112">返回时, 包含返回的配置文件名称的实际长度, 包括0终止字符。</span><span class="sxs-lookup"><span data-stu-id="75a1c-112">Upon return, contains the actual length, including the 0-terminating character, of the returned profile name.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="75a1c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="75a1c-113">Return values</span></span>

|<span data-ttu-id="75a1c-114">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="75a1c-114">**HRESULT**</span></span>|<span data-ttu-id="75a1c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="75a1c-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75a1c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="75a1c-116">S_OK</span></span>  <br/> |<span data-ttu-id="75a1c-117">调用成功。</span><span class="sxs-lookup"><span data-stu-id="75a1c-117">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="75a1c-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="75a1c-118">E_OUTOFMEMORY</span></span>  <br/> |<span data-ttu-id="75a1c-119">返回的配置文件名称的长度大于_pwszIdentity_的大小。</span><span class="sxs-lookup"><span data-stu-id="75a1c-119">The returned profile name is longer than the size of  _pwszIdentity_.</span></span>  <br/> |
|<span data-ttu-id="75a1c-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="75a1c-120">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="75a1c-121">_pcch_为 NULL。</span><span class="sxs-lookup"><span data-stu-id="75a1c-121">_pcch_ is NULL.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="75a1c-122">注解</span><span class="sxs-lookup"><span data-stu-id="75a1c-122">Remarks</span></span>

<span data-ttu-id="75a1c-123">如果_pwszIdentity_太小, 不能容纳配置文件名, 则不会在返回时设置它, 并且_pcch_将指向_pwszIdentity_所需的大小。</span><span class="sxs-lookup"><span data-stu-id="75a1c-123">If  _pwszIdentity_ is too small to hold the profile name, it will not be set on return, and  _pcch_ will point to the size required for  _pwszIdentity_.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75a1c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75a1c-124">See also</span></span>

- [<span data-ttu-id="75a1c-125">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="75a1c-125">About the Account Management API</span></span>](about-the-account-management-api.md)
- [<span data-ttu-id="75a1c-126">PidTagProfileName</span><span class="sxs-lookup"><span data-stu-id="75a1c-126">PidTagProfileName</span></span>](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx)

