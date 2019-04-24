---
title: PROP_ACCT_SENTITEMS_EID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f199a97f-55d6-9297-adc4-e9f7b4b5f58b
description: 代表帐户的已发送项目的默认文件夹的条目 ID。
ms.openlocfilehash: 24bb4714a4f4964ac3d84ea7a792e64da67599df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327585"
---
# <a name="propacctsentitemseid"></a><span data-ttu-id="50d38-103">PROP_ACCT_SENTITEMS_EID</span><span class="sxs-lookup"><span data-stu-id="50d38-103">PROP_ACCT_SENTITEMS_EID</span></span>

<span data-ttu-id="50d38-104">代表帐户的已发送项目的默认文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="50d38-104">Represents the Entry ID of the default folder for sent items for the account.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="50d38-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="50d38-105">Quick info</span></span>

<span data-ttu-id="50d38-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="50d38-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="50d38-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="50d38-107">Identifier:</span></span>  <br/> |<span data-ttu-id="50d38-108">0x0020</span><span class="sxs-lookup"><span data-stu-id="50d38-108">0x0020</span></span>  <br/> |
|<span data-ttu-id="50d38-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="50d38-109">Property type:</span></span>  <br/> |<span data-ttu-id="50d38-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="50d38-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="50d38-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="50d38-111">Property tag:</span></span>  <br/> |<span data-ttu-id="50d38-112">0x00200102</span><span class="sxs-lookup"><span data-stu-id="50d38-112">0x00200102</span></span>  <br/> |
|<span data-ttu-id="50d38-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="50d38-113">Access:</span></span>  <br/> |<span data-ttu-id="50d38-114">只读</span><span class="sxs-lookup"><span data-stu-id="50d38-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="50d38-115">注解</span><span class="sxs-lookup"><span data-stu-id="50d38-115">Remarks</span></span>

<span data-ttu-id="50d38-116">使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="50d38-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span>
  
<span data-ttu-id="50d38-117">"已发送邮件" 的默认文件夹为 "已**发送**邮件"。</span><span class="sxs-lookup"><span data-stu-id="50d38-117">The default folder for sent items is **Sent Items**.</span></span>
  
<span data-ttu-id="50d38-118">对于 POP3 和 IMAP 帐户, 此属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="50d38-118">This property is read-only for POP3 and IMAP accounts.</span></span> <span data-ttu-id="50d38-119">尝试为这些类型的帐户设置此属性将返回**E_ACCT_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="50d38-119">Attempting to set this property for these types of accounts returns **E_ACCT_NOT_FOUND**.</span></span> 
  

