---
title: 实现标准窗体谓词
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f89f7c58-6358-4523-9788-676f189b5e69
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6360b86dc23a5404b818f76cb1c2cd10747ef3cb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426119"
---
# <a name="implementing-standard-form-verbs"></a><span data-ttu-id="b9877-103">实现标准窗体谓词</span><span class="sxs-lookup"><span data-stu-id="b9877-103">Implementing Standard Form Verbs</span></span>

  
  
<span data-ttu-id="b9877-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9877-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9877-105">MAPI 定义了一组标准谓词, 或在用户做出菜单选择或单击按钮 (所有表单查看器都应支持) 时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b9877-105">MAPI defines a set of standard verbs, or actions taken when a user makes a menu selection or clicks a button, that all form viewers should support.</span></span> <span data-ttu-id="b9877-106">每个动词都有一个与之相关联的常量, 用于标识, 在 EXCHFORM 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="b9877-106">Each verb has a constant associated with it for identification, defined in the EXCHFORM.H header file.</span></span> <span data-ttu-id="b9877-107">下表列出了标准窗体谓词及其关联的常量:</span><span class="sxs-lookup"><span data-stu-id="b9877-107">The following table lists the standard form verbs and their associated constants:</span></span>
  
|<span data-ttu-id="b9877-108">**Verb**</span><span class="sxs-lookup"><span data-stu-id="b9877-108">**Verb**</span></span>|<span data-ttu-id="b9877-109">**值**</span><span class="sxs-lookup"><span data-stu-id="b9877-109">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9877-110">打开</span><span class="sxs-lookup"><span data-stu-id="b9877-110">Open</span></span>  <br/> |<span data-ttu-id="b9877-111">EXCHIVERB_OPEN</span><span class="sxs-lookup"><span data-stu-id="b9877-111">EXCHIVERB_OPEN</span></span>  <br/> |
|<span data-ttu-id="b9877-112">回复</span><span class="sxs-lookup"><span data-stu-id="b9877-112">Reply</span></span>  <br/> |<span data-ttu-id="b9877-113">EXCHIVERB_REPLYTOSENDER</span><span class="sxs-lookup"><span data-stu-id="b9877-113">EXCHIVERB_REPLYTOSENDER</span></span>  <br/> |
|<span data-ttu-id="b9877-114">全部答复</span><span class="sxs-lookup"><span data-stu-id="b9877-114">Reply to All</span></span>  <br/> |<span data-ttu-id="b9877-115">EXCHIVERB_REPLYTOALL</span><span class="sxs-lookup"><span data-stu-id="b9877-115">EXCHIVERB_REPLYTOALL</span></span>  <br/> |
|<span data-ttu-id="b9877-116">前后</span><span class="sxs-lookup"><span data-stu-id="b9877-116">Forward</span></span>  <br/> |<span data-ttu-id="b9877-117">EXCHIVERB_FORWARD</span><span class="sxs-lookup"><span data-stu-id="b9877-117">EXCHIVERB_FORWARD</span></span>  <br/> |
|<span data-ttu-id="b9877-118">Print</span><span class="sxs-lookup"><span data-stu-id="b9877-118">Print</span></span>  <br/> |<span data-ttu-id="b9877-119">EXCHIVERB_PRINT</span><span class="sxs-lookup"><span data-stu-id="b9877-119">EXCHIVERB_PRINT</span></span>  <br/> |
|<span data-ttu-id="b9877-120">另存为</span><span class="sxs-lookup"><span data-stu-id="b9877-120">Save As</span></span>  <br/> |<span data-ttu-id="b9877-121">EXCHIVERB_SAVEAS</span><span class="sxs-lookup"><span data-stu-id="b9877-121">EXCHIVERB_SAVEAS</span></span>  <br/> |
|<span data-ttu-id="b9877-122">答复到文件夹</span><span class="sxs-lookup"><span data-stu-id="b9877-122">Reply to Folder</span></span>  <br/> |<span data-ttu-id="b9877-123">EXCHIVERB_REPLYTOFOLDER</span><span class="sxs-lookup"><span data-stu-id="b9877-123">EXCHIVERB_REPLYTOFOLDER</span></span>  <br/> |
   
<span data-ttu-id="b9877-124">当用户选择某个谓词时, 在对该窗体的 IMAPIForm 的调用中传递其常量[::D overb](imapiform-doverb.md)方法执行其对应的操作。</span><span class="sxs-lookup"><span data-stu-id="b9877-124">When a user chooses a verb, pass its constant in a call to the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method to perform its corresponding action.</span></span> 
  
<span data-ttu-id="b9877-125">除了通过表单查看器访问谓词之外, 用户有时还可以直接从窗体访问谓词。</span><span class="sxs-lookup"><span data-stu-id="b9877-125">In addition to accessing verbs through your form viewer, users can sometimes access verbs directly from the form.</span></span> <span data-ttu-id="b9877-126">例如, 某些表单对象允许用户通过右键单击表单并从上下文相关的菜单中选择 "**打印**" 来调用**打印**谓词。</span><span class="sxs-lookup"><span data-stu-id="b9877-126">For example, some form objects allow the user to invoke the **Print** verb by right-clicking on the form and choosing **Print** from a context-sensitive menu.</span></span> 
  

