---
title: PROP_ACCT_SEND_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b86242f3-dfd7-398e-a054-93db85b69752
description: 返回 accountsendstamp。
ms.openlocfilehash: d860a117e4ab5470f84ff1807cb6246cd852d24b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423004"
---
# <a name="prop_acct_send_stamp"></a><span data-ttu-id="30c4b-103">PROP_ACCT_SEND_STAMP</span><span class="sxs-lookup"><span data-stu-id="30c4b-103">PROP_ACCT_SEND_STAMP</span></span>

<span data-ttu-id="30c4b-104">返回帐户"send"标记。</span><span class="sxs-lookup"><span data-stu-id="30c4b-104">Returns the account "send" stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="30c4b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="30c4b-105">Quick info</span></span>

<span data-ttu-id="30c4b-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="30c4b-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="30c4b-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="30c4b-107">Identifier:</span></span>  <br/> |<span data-ttu-id="30c4b-108">0x000E</span><span class="sxs-lookup"><span data-stu-id="30c4b-108">0x000E</span></span>  <br/> |
|<span data-ttu-id="30c4b-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="30c4b-109">Property type:</span></span>  <br/> |<span data-ttu-id="30c4b-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="30c4b-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="30c4b-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="30c4b-111">Property tag:</span></span>  <br/> |<span data-ttu-id="30c4b-112">0x000E001F</span><span class="sxs-lookup"><span data-stu-id="30c4b-112">0x000E001F</span></span>  <br/> |
|<span data-ttu-id="30c4b-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="30c4b-113">Access:</span></span>  <br/> |<span data-ttu-id="30c4b-114">只读</span><span class="sxs-lookup"><span data-stu-id="30c4b-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="30c4b-115">备注</span><span class="sxs-lookup"><span data-stu-id="30c4b-115">Remarks</span></span>

<span data-ttu-id="30c4b-116">使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。</span><span class="sxs-lookup"><span data-stu-id="30c4b-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="30c4b-117">如果客户端尝试设置此属性，则此属性返回 E_OLK_PROP_READ_ONLY **。**</span><span class="sxs-lookup"><span data-stu-id="30c4b-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="30c4b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30c4b-118">See also</span></span>

- [<span data-ttu-id="30c4b-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="30c4b-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="30c4b-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="30c4b-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

