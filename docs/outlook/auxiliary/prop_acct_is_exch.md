---
title: PROP_ACCT_IS_EXCH
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 599bfc7d-7b62-7cc1-69ff-6db04c96a49b
description: 如果帐户是 Exchange 帐户, 则为 True。
ms.openlocfilehash: 2df750b208ff9d2a18cb0d7c22ec6b32b658c7b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418230"
---
# <a name="propacctisexch"></a><span data-ttu-id="76bcc-103">PROP_ACCT_IS_EXCH</span><span class="sxs-lookup"><span data-stu-id="76bcc-103">PROP_ACCT_IS_EXCH</span></span>

<span data-ttu-id="76bcc-104">如果帐户是 Exchange 帐户, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="76bcc-104">True if the account is an Exchange account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="76bcc-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="76bcc-105">Quick info</span></span>

<span data-ttu-id="76bcc-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="76bcc-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="76bcc-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="76bcc-107">Identifier:</span></span>  <br/> |<span data-ttu-id="76bcc-108">0x0014</span><span class="sxs-lookup"><span data-stu-id="76bcc-108">0x0014</span></span>  <br/> |
|<span data-ttu-id="76bcc-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="76bcc-109">Property type:</span></span>  <br/> |<span data-ttu-id="76bcc-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="76bcc-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="76bcc-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="76bcc-111">Property tag:</span></span>  <br/> |<span data-ttu-id="76bcc-112">0x00140003</span><span class="sxs-lookup"><span data-stu-id="76bcc-112">0x00140003</span></span>  <br/> |
|<span data-ttu-id="76bcc-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="76bcc-113">Access:</span></span>  <br/> |<span data-ttu-id="76bcc-114">只读</span><span class="sxs-lookup"><span data-stu-id="76bcc-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="76bcc-115">说明</span><span class="sxs-lookup"><span data-stu-id="76bcc-115">Remarks</span></span>

<span data-ttu-id="76bcc-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="76bcc-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="76bcc-117">如果客户端尝试设置此属性, 则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="76bcc-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="76bcc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76bcc-118">See also</span></span>

- [<span data-ttu-id="76bcc-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="76bcc-119">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="76bcc-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="76bcc-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

