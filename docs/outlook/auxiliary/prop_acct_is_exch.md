---
title: PROP_ACCT_IS_EXCH
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 599bfc7d-7b62-7cc1-69ff-6db04c96a49b
description: 如果该帐户是 Exchange 帐户，则为 true。
ms.openlocfilehash: db9f5ae46096d221ac3636a44f588c6a90ce146e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774422"
---
# <a name="propacctisexch"></a><span data-ttu-id="69e56-103">PROP_ACCT_IS_EXCH</span><span class="sxs-lookup"><span data-stu-id="69e56-103">PROP_ACCT_IS_EXCH</span></span>

<span data-ttu-id="69e56-104">如果该帐户是 Exchange 帐户，则为 true。</span><span class="sxs-lookup"><span data-stu-id="69e56-104">True if the account is an Exchange account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="69e56-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="69e56-105">Quick info</span></span>

<span data-ttu-id="69e56-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="69e56-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="69e56-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="69e56-107">Identifier:</span></span>  <br/> |<span data-ttu-id="69e56-108">0x0014</span><span class="sxs-lookup"><span data-stu-id="69e56-108">0x0014</span></span>  <br/> |
|<span data-ttu-id="69e56-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="69e56-109">Property type:</span></span>  <br/> |<span data-ttu-id="69e56-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="69e56-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="69e56-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="69e56-111">Property tag:</span></span>  <br/> |<span data-ttu-id="69e56-112">0x00140003</span><span class="sxs-lookup"><span data-stu-id="69e56-112">0x00140003</span></span>  <br/> |
|<span data-ttu-id="69e56-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="69e56-113">Access:</span></span>  <br/> |<span data-ttu-id="69e56-114">只读</span><span class="sxs-lookup"><span data-stu-id="69e56-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="69e56-115">说明</span><span class="sxs-lookup"><span data-stu-id="69e56-115">Remarks</span></span>

<span data-ttu-id="69e56-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="69e56-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="69e56-117">如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="69e56-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="69e56-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69e56-118">See also</span></span>

- [<span data-ttu-id="69e56-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="69e56-119">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="69e56-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="69e56-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

