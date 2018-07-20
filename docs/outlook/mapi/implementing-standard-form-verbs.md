---
title: 实现标准窗体谓词
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f89f7c58-6358-4523-9788-676f189b5e69
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8135af7947f30ac600b8d9af364b2a79a3443ab6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775823"
---
# <a name="implementing-standard-form-verbs"></a><span data-ttu-id="5ea0f-103">实现标准窗体谓词</span><span class="sxs-lookup"><span data-stu-id="5ea0f-103">Implementing Standard Form Verbs</span></span>

  
  
<span data-ttu-id="5ea0f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5ea0f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5ea0f-105">MAPI 定义一组标准谓词或用户选择了菜单或单击按钮时，所有表单查看器应支持时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5ea0f-105">MAPI defines a set of standard verbs, or actions taken when a user makes a menu selection or clicks a button, that all form viewers should support.</span></span> <span data-ttu-id="5ea0f-106">每个动作具有与之关联的标识，EXCHFORM 中定义的常量。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="5ea0f-106">Each verb has a constant associated with it for identification, defined in the EXCHFORM.H header file.</span></span> <span data-ttu-id="5ea0f-107">下表列出的标准窗体谓词和其关联的常量：</span><span class="sxs-lookup"><span data-stu-id="5ea0f-107">The following table lists the standard form verbs and their associated constants:</span></span>
  
|<span data-ttu-id="5ea0f-108">**谓词**</span><span class="sxs-lookup"><span data-stu-id="5ea0f-108">**Verb**</span></span>|<span data-ttu-id="5ea0f-109">**值**</span><span class="sxs-lookup"><span data-stu-id="5ea0f-109">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5ea0f-110">打开</span><span class="sxs-lookup"><span data-stu-id="5ea0f-110">Open</span></span>  <br/> |<span data-ttu-id="5ea0f-111">EXCHIVERB_OPEN</span><span class="sxs-lookup"><span data-stu-id="5ea0f-111">EXCHIVERB_OPEN</span></span>  <br/> |
|<span data-ttu-id="5ea0f-112">答复</span><span class="sxs-lookup"><span data-stu-id="5ea0f-112">Reply</span></span>  <br/> |<span data-ttu-id="5ea0f-113">EXCHIVERB_REPLYTOSENDER</span><span class="sxs-lookup"><span data-stu-id="5ea0f-113">EXCHIVERB_REPLYTOSENDER</span></span>  <br/> |
|<span data-ttu-id="5ea0f-114">全部答复</span><span class="sxs-lookup"><span data-stu-id="5ea0f-114">Reply to All</span></span>  <br/> |<span data-ttu-id="5ea0f-115">EXCHIVERB_REPLYTOALL</span><span class="sxs-lookup"><span data-stu-id="5ea0f-115">EXCHIVERB_REPLYTOALL</span></span>  <br/> |
|<span data-ttu-id="5ea0f-116">Forward</span><span class="sxs-lookup"><span data-stu-id="5ea0f-116">Forward</span></span>  <br/> |<span data-ttu-id="5ea0f-117">EXCHIVERB_FORWARD</span><span class="sxs-lookup"><span data-stu-id="5ea0f-117">EXCHIVERB_FORWARD</span></span>  <br/> |
|<span data-ttu-id="5ea0f-118">打印</span><span class="sxs-lookup"><span data-stu-id="5ea0f-118">Print</span></span>  <br/> |<span data-ttu-id="5ea0f-119">EXCHIVERB_PRINT</span><span class="sxs-lookup"><span data-stu-id="5ea0f-119">EXCHIVERB_PRINT</span></span>  <br/> |
|<span data-ttu-id="5ea0f-120">另存为</span><span class="sxs-lookup"><span data-stu-id="5ea0f-120">Save As</span></span>  <br/> |<span data-ttu-id="5ea0f-121">EXCHIVERB_SAVEAS</span><span class="sxs-lookup"><span data-stu-id="5ea0f-121">EXCHIVERB_SAVEAS</span></span>  <br/> |
|<span data-ttu-id="5ea0f-122">答复到文件夹</span><span class="sxs-lookup"><span data-stu-id="5ea0f-122">Reply to Folder</span></span>  <br/> |<span data-ttu-id="5ea0f-123">EXCHIVERB_REPLYTOFOLDER</span><span class="sxs-lookup"><span data-stu-id="5ea0f-123">EXCHIVERB_REPLYTOFOLDER</span></span>  <br/> |
   
<span data-ttu-id="5ea0f-124">当用户选择一个谓词时，传递窗体的[IMAPIForm::DoVerb](imapiform-doverb.md)方法执行其相应的操作将调用其常量。</span><span class="sxs-lookup"><span data-stu-id="5ea0f-124">When a user chooses a verb, pass its constant in a call to the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method to perform its corresponding action.</span></span> 
  
<span data-ttu-id="5ea0f-125">除了通过您的表单查看器中访问谓词，用户可以有时访问直接从窗体的动作。</span><span class="sxs-lookup"><span data-stu-id="5ea0f-125">In addition to accessing verbs through your form viewer, users can sometimes access verbs directly from the form.</span></span> <span data-ttu-id="5ea0f-126">例如，某些窗体对象允许用户通过右键单击窗体上并从上下文相关的菜单中选择**打印**调用**打印**动词。</span><span class="sxs-lookup"><span data-stu-id="5ea0f-126">For example, some form objects allow the user to invoke the **Print** verb by right-clicking on the form and choosing **Print** from a context-sensitive menu.</span></span> 
  
