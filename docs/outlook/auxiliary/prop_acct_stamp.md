---
title: PROP_ACCT_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70b6ecc8-6be3-0f05-3291-ac5b7f2ecfdb
description: 返回帐户戳。
ms.openlocfilehash: ec1824d8c8c61d392b4e11cdb5213a85100d971e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19774445"
---
# <a name="propacctstamp"></a><span data-ttu-id="d7cdf-103">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="d7cdf-103">PROP_ACCT_STAMP</span></span>

<span data-ttu-id="d7cdf-104">返回帐户戳。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-104">Returns the account stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d7cdf-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d7cdf-105">Quick info</span></span>

<span data-ttu-id="d7cdf-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="d7cdf-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d7cdf-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="d7cdf-107">Identifier:</span></span>  <br/> |<span data-ttu-id="d7cdf-108">0x000D</span><span class="sxs-lookup"><span data-stu-id="d7cdf-108">0x000D</span></span>  <br/> |
|<span data-ttu-id="d7cdf-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="d7cdf-109">Property type:</span></span>  <br/> |<span data-ttu-id="d7cdf-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d7cdf-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d7cdf-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="d7cdf-111">Property tag:</span></span>  <br/> |<span data-ttu-id="d7cdf-112">0x000D001F</span><span class="sxs-lookup"><span data-stu-id="d7cdf-112">0x000D001F</span></span>  <br/> |
|<span data-ttu-id="d7cdf-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="d7cdf-113">Access:</span></span>  <br/> |<span data-ttu-id="d7cdf-114">只读</span><span class="sxs-lookup"><span data-stu-id="d7cdf-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d7cdf-115">备注</span><span class="sxs-lookup"><span data-stu-id="d7cdf-115">Remarks</span></span>

<span data-ttu-id="d7cdf-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="d7cdf-117">如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="d7cdf-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7cdf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7cdf-118">See also</span></span>

- [<span data-ttu-id="d7cdf-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="d7cdf-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="d7cdf-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="d7cdf-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

