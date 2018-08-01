---
title: PROP_ACCT_SEND_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b86242f3-dfd7-398e-a054-93db85b69752
description: 返回 accountsendstamp。
ms.openlocfilehash: 948855f32ecd83334e2ab2af0926fedb0e6d7f84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774426"
---
# <a name="propacctsendstamp"></a><span data-ttu-id="3c445-103">PROP_ACCT_SEND_STAMP</span><span class="sxs-lookup"><span data-stu-id="3c445-103">PROP_ACCT_SEND_STAMP</span></span>

<span data-ttu-id="3c445-104">返回的帐户"发送"戳。</span><span class="sxs-lookup"><span data-stu-id="3c445-104">Returns the account "send" stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="3c445-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="3c445-105">Quick info</span></span>

<span data-ttu-id="3c445-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="3c445-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3c445-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="3c445-107">Identifier:</span></span>  <br/> |<span data-ttu-id="3c445-108">0x000E</span><span class="sxs-lookup"><span data-stu-id="3c445-108">0x000E</span></span>  <br/> |
|<span data-ttu-id="3c445-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="3c445-109">Property type:</span></span>  <br/> |<span data-ttu-id="3c445-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3c445-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3c445-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="3c445-111">Property tag:</span></span>  <br/> |<span data-ttu-id="3c445-112">0x000E001F</span><span class="sxs-lookup"><span data-stu-id="3c445-112">0x000E001F</span></span>  <br/> |
|<span data-ttu-id="3c445-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="3c445-113">Access:</span></span>  <br/> |<span data-ttu-id="3c445-114">只读</span><span class="sxs-lookup"><span data-stu-id="3c445-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3c445-115">说明</span><span class="sxs-lookup"><span data-stu-id="3c445-115">Remarks</span></span>

<span data-ttu-id="3c445-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="3c445-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="3c445-117">如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="3c445-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c445-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c445-118">See also</span></span>

- [<span data-ttu-id="3c445-119">有关帐户管理 API</span><span class="sxs-lookup"><span data-stu-id="3c445-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="3c445-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="3c445-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

