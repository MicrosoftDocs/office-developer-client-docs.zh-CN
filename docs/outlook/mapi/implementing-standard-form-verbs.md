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
# <a name="implementing-standard-form-verbs"></a><span data-ttu-id="6205d-103">实现标准窗体谓词</span><span class="sxs-lookup"><span data-stu-id="6205d-103">Implementing Standard Form Verbs</span></span>

  
  
<span data-ttu-id="6205d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6205d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6205d-105">MAPI 定义一组所有表单查看者都应支持的标准动词或当用户选择菜单或单击按钮时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="6205d-105">MAPI defines a set of standard verbs, or actions taken when a user makes a menu selection or clicks a button, that all form viewers should support.</span></span> <span data-ttu-id="6205d-106">每个动词都有一个与之关联的常量，用于标识，该常量在 EXCHFORM 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="6205d-106">Each verb has a constant associated with it for identification, defined in the EXCHFORM.H header file.</span></span> <span data-ttu-id="6205d-107">下表列出了标准窗体动词及其关联的常量：</span><span class="sxs-lookup"><span data-stu-id="6205d-107">The following table lists the standard form verbs and their associated constants:</span></span>
  
|<span data-ttu-id="6205d-108">**Verb**</span><span class="sxs-lookup"><span data-stu-id="6205d-108">**Verb**</span></span>|<span data-ttu-id="6205d-109">**值**</span><span class="sxs-lookup"><span data-stu-id="6205d-109">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6205d-110">打开</span><span class="sxs-lookup"><span data-stu-id="6205d-110">Open</span></span>  <br/> |<span data-ttu-id="6205d-111">EXCHIVERB_OPEN</span><span class="sxs-lookup"><span data-stu-id="6205d-111">EXCHIVERB_OPEN</span></span>  <br/> |
|<span data-ttu-id="6205d-112">答复</span><span class="sxs-lookup"><span data-stu-id="6205d-112">Reply</span></span>  <br/> |<span data-ttu-id="6205d-113">EXCHIVERB_REPLYTOSENDER</span><span class="sxs-lookup"><span data-stu-id="6205d-113">EXCHIVERB_REPLYTOSENDER</span></span>  <br/> |
|<span data-ttu-id="6205d-114">全部答复</span><span class="sxs-lookup"><span data-stu-id="6205d-114">Reply to All</span></span>  <br/> |<span data-ttu-id="6205d-115">EXCHIVERB_REPLYTOALL</span><span class="sxs-lookup"><span data-stu-id="6205d-115">EXCHIVERB_REPLYTOALL</span></span>  <br/> |
|<span data-ttu-id="6205d-116">转发</span><span class="sxs-lookup"><span data-stu-id="6205d-116">Forward</span></span>  <br/> |<span data-ttu-id="6205d-117">EXCHIVERB_FORWARD</span><span class="sxs-lookup"><span data-stu-id="6205d-117">EXCHIVERB_FORWARD</span></span>  <br/> |
|<span data-ttu-id="6205d-118">打印</span><span class="sxs-lookup"><span data-stu-id="6205d-118">Print</span></span>  <br/> |<span data-ttu-id="6205d-119">EXCHIVERB_PRINT</span><span class="sxs-lookup"><span data-stu-id="6205d-119">EXCHIVERB_PRINT</span></span>  <br/> |
|<span data-ttu-id="6205d-120">另存为</span><span class="sxs-lookup"><span data-stu-id="6205d-120">Save As</span></span>  <br/> |<span data-ttu-id="6205d-121">EXCHIVERB_SAVEAS</span><span class="sxs-lookup"><span data-stu-id="6205d-121">EXCHIVERB_SAVEAS</span></span>  <br/> |
|<span data-ttu-id="6205d-122">答复到文件夹</span><span class="sxs-lookup"><span data-stu-id="6205d-122">Reply to Folder</span></span>  <br/> |<span data-ttu-id="6205d-123">EXCHIVERB_REPLYTOFOLDER</span><span class="sxs-lookup"><span data-stu-id="6205d-123">EXCHIVERB_REPLYTOFOLDER</span></span>  <br/> |
   
<span data-ttu-id="6205d-124">当用户选择一个动词时，在调用表单 [的 IMAPIForm：:D oVerb](imapiform-doverb.md) 方法中传递其常量以执行其相应的操作。</span><span class="sxs-lookup"><span data-stu-id="6205d-124">When a user chooses a verb, pass its constant in a call to the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method to perform its corresponding action.</span></span> 
  
<span data-ttu-id="6205d-125">除了通过表单查看器访问动词之外，用户有时还可以直接从窗体访问动词。</span><span class="sxs-lookup"><span data-stu-id="6205d-125">In addition to accessing verbs through your form viewer, users can sometimes access verbs directly from the form.</span></span> <span data-ttu-id="6205d-126">例如，某些表单对象允许用户通过右键单击表单，然后从上下文相关菜单中选择"打印"来调用 **Print** 动词。</span><span class="sxs-lookup"><span data-stu-id="6205d-126">For example, some form objects allow the user to invoke the **Print** verb by right-clicking on the form and choosing **Print** from a context-sensitive menu.</span></span> 
  

