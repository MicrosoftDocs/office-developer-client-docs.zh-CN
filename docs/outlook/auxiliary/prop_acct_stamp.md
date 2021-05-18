---
title: PROP_ACCT_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70b6ecc8-6be3-0f05-3291-ac5b7f2ecfdb
description: 返回帐户标记。
ms.openlocfilehash: fe3c6e65e12ab62bd1c2ec0245e4a22502f610eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408248"
---
# <a name="prop_acct_stamp"></a><span data-ttu-id="fcfb8-103">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="fcfb8-103">PROP_ACCT_STAMP</span></span>

<span data-ttu-id="fcfb8-104">返回帐户标记。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-104">Returns the account stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fcfb8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="fcfb8-105">Quick info</span></span>

<span data-ttu-id="fcfb8-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="fcfb8-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fcfb8-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="fcfb8-107">Identifier:</span></span>  <br/> |<span data-ttu-id="fcfb8-108">0x000D</span><span class="sxs-lookup"><span data-stu-id="fcfb8-108">0x000D</span></span>  <br/> |
|<span data-ttu-id="fcfb8-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="fcfb8-109">Property type:</span></span>  <br/> |<span data-ttu-id="fcfb8-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fcfb8-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="fcfb8-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="fcfb8-111">Property tag:</span></span>  <br/> |<span data-ttu-id="fcfb8-112">0x000D001F</span><span class="sxs-lookup"><span data-stu-id="fcfb8-112">0x000D001F</span></span>  <br/> |
|<span data-ttu-id="fcfb8-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="fcfb8-113">Access:</span></span>  <br/> |<span data-ttu-id="fcfb8-114">只读</span><span class="sxs-lookup"><span data-stu-id="fcfb8-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fcfb8-115">备注</span><span class="sxs-lookup"><span data-stu-id="fcfb8-115">Remarks</span></span>

<span data-ttu-id="fcfb8-116">使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。</span><span class="sxs-lookup"><span data-stu-id="fcfb8-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="fcfb8-117">如果客户端尝试设置此属性，则此属性返回 E_OLK_PROP_READ_ONLY **。**</span><span class="sxs-lookup"><span data-stu-id="fcfb8-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fcfb8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcfb8-118">See also</span></span>

- [<span data-ttu-id="fcfb8-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="fcfb8-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="fcfb8-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="fcfb8-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

