---
title: PROP_ACCT_SENTITEMS_EID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f199a97f-55d6-9297-adc4-e9f7b4b5f58b
description: 表示的帐户已发送邮件的默认文件夹的条目 ID。
ms.openlocfilehash: 7795e8a112f0575b764fd55e92d27c7085e3d3a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774428"
---
# <a name="propacctsentitemseid"></a><span data-ttu-id="8ca31-103">PROP_ACCT_SENTITEMS_EID</span><span class="sxs-lookup"><span data-stu-id="8ca31-103">PROP_ACCT_SENTITEMS_EID</span></span>

<span data-ttu-id="8ca31-104">表示的帐户已发送邮件的默认文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="8ca31-104">Represents the Entry ID of the default folder for sent items for the account.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="8ca31-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="8ca31-105">Quick info</span></span>

<span data-ttu-id="8ca31-106">See [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="8ca31-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8ca31-107">标识符:</span><span class="sxs-lookup"><span data-stu-id="8ca31-107">Identifier:</span></span>  <br/> |<span data-ttu-id="8ca31-108">0x0020</span><span class="sxs-lookup"><span data-stu-id="8ca31-108">0x0020</span></span>  <br/> |
|<span data-ttu-id="8ca31-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="8ca31-109">Property type:</span></span>  <br/> |<span data-ttu-id="8ca31-110">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8ca31-110">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8ca31-111">属性标记：</span><span class="sxs-lookup"><span data-stu-id="8ca31-111">Property tag:</span></span>  <br/> |<span data-ttu-id="8ca31-112">0x00200102</span><span class="sxs-lookup"><span data-stu-id="8ca31-112">0x00200102</span></span>  <br/> |
|<span data-ttu-id="8ca31-113">访问权限</span><span class="sxs-lookup"><span data-stu-id="8ca31-113">Access:</span></span>  <br/> |<span data-ttu-id="8ca31-114">只读</span><span class="sxs-lookup"><span data-stu-id="8ca31-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8ca31-115">说明</span><span class="sxs-lookup"><span data-stu-id="8ca31-115">Remarks</span></span>

<span data-ttu-id="8ca31-116">通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。</span><span class="sxs-lookup"><span data-stu-id="8ca31-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span>
  
<span data-ttu-id="8ca31-117">已发送邮件的默认文件夹是**已发送邮件**。</span><span class="sxs-lookup"><span data-stu-id="8ca31-117">The default folder for sent items is **Sent Items**.</span></span>
  
<span data-ttu-id="8ca31-118">此属性是只读的 POP3 和 IMAP 帐户。</span><span class="sxs-lookup"><span data-stu-id="8ca31-118">This property is read-only for POP3 and IMAP accounts.</span></span> <span data-ttu-id="8ca31-119">试图对这些类型的帐户设置此属性返回**E_ACCT_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="8ca31-119">Attempting to set this property for these types of accounts returns **E_ACCT_NOT_FOUND**.</span></span> 
  

