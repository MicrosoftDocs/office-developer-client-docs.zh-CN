---
title: PROP_ACCT_IS_EXCH
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 599bfc7d-7b62-7cc1-69ff-6db04c96a49b
description: 如此 如果该帐户是一个Exchange帐户。
ms.openlocfilehash: 2df750b208ff9d2a18cb0d7c22ec6b32b658c7b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418230"
---
# <a name="prop_acct_is_exch"></a><span data-ttu-id="72556-103">PROP_ACCT_IS_EXCH</span><span class="sxs-lookup"><span data-stu-id="72556-103">PROP_ACCT_IS_EXCH</span></span>

<span data-ttu-id="72556-104">如此 如果该帐户是一个Exchange帐户。</span><span class="sxs-lookup"><span data-stu-id="72556-104">True if the account is an Exchange account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="72556-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="72556-105">Quick info</span></span>

<span data-ttu-id="72556-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="72556-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="72556-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="72556-107">Identifier:</span></span>  <br/> |<span data-ttu-id="72556-108">0x0014</span><span class="sxs-lookup"><span data-stu-id="72556-108">0x0014</span></span>  <br/> |
|<span data-ttu-id="72556-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="72556-109">Property type:</span></span>  <br/> |<span data-ttu-id="72556-110">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="72556-110">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="72556-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="72556-111">Property tag:</span></span>  <br/> |<span data-ttu-id="72556-112">0x00140003</span><span class="sxs-lookup"><span data-stu-id="72556-112">0x00140003</span></span>  <br/> |
|<span data-ttu-id="72556-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="72556-113">Access:</span></span>  <br/> |<span data-ttu-id="72556-114">只读</span><span class="sxs-lookup"><span data-stu-id="72556-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="72556-115">备注</span><span class="sxs-lookup"><span data-stu-id="72556-115">Remarks</span></span>

<span data-ttu-id="72556-116">使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。</span><span class="sxs-lookup"><span data-stu-id="72556-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="72556-117">如果客户端尝试设置此属性，则此属性返回 E_OLK_PROP_READ_ONLY **。**</span><span class="sxs-lookup"><span data-stu-id="72556-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="72556-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72556-118">See also</span></span>

- [<span data-ttu-id="72556-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="72556-119">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="72556-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="72556-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

