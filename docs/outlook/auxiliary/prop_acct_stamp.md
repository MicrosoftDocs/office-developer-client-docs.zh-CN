---
title: PROP_ACCT_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70b6ecc8-6be3-0f05-3291-ac5b7f2ecfdb
description: 返回帐户戳。
ms.openlocfilehash: fe3c6e65e12ab62bd1c2ec0245e4a22502f610eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327592"
---
# <a name="propacctstamp"></a><span data-ttu-id="ab165-103">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="ab165-103">PROP_ACCT_STAMP</span></span>

<span data-ttu-id="ab165-104">返回帐户戳。</span><span class="sxs-lookup"><span data-stu-id="ab165-104">Returns the account stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="ab165-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="ab165-105">Quick info</span></span>

<span data-ttu-id="ab165-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="ab165-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ab165-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="ab165-107">Identifier:</span></span>  <br/> |<span data-ttu-id="ab165-108">0x000D</span><span class="sxs-lookup"><span data-stu-id="ab165-108">0x000D</span></span>  <br/> |
|<span data-ttu-id="ab165-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="ab165-109">Property type:</span></span>  <br/> |<span data-ttu-id="ab165-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ab165-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ab165-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="ab165-111">Property tag:</span></span>  <br/> |<span data-ttu-id="ab165-112">0x000D001F</span><span class="sxs-lookup"><span data-stu-id="ab165-112">0x000D001F</span></span>  <br/> |
|<span data-ttu-id="ab165-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="ab165-113">Access:</span></span>  <br/> |<span data-ttu-id="ab165-114">只读</span><span class="sxs-lookup"><span data-stu-id="ab165-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ab165-115">注解</span><span class="sxs-lookup"><span data-stu-id="ab165-115">Remarks</span></span>

<span data-ttu-id="ab165-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="ab165-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="ab165-117">如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="ab165-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ab165-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab165-118">See also</span></span>

- [<span data-ttu-id="ab165-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="ab165-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="ab165-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="ab165-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

