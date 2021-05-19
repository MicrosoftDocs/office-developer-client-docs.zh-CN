---
title: Form Configuration File [Verbs] Section
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bb7d49d69fadab54212ff7e8b50ac969e4890c0a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417782"
---
# <a name="form-configuration-file-verbs-section"></a><span data-ttu-id="f7e30-103">Form Configuration File [Verbs] Section</span><span class="sxs-lookup"><span data-stu-id="f7e30-103">Form Configuration File [Verbs] Section</span></span>

  
  
<span data-ttu-id="f7e30-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7e30-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7e30-105">**[Verbs]** 节列出了表单支持的完整动词集。</span><span class="sxs-lookup"><span data-stu-id="f7e30-105">The **[Verbs]** section lists the complete set of verbs supported by the form.</span></span> <span data-ttu-id="f7e30-106">**[Verbs]** 节的格式为：</span><span class="sxs-lookup"><span data-stu-id="f7e30-106">The format of the **[Verbs]** section is:</span></span> 
  
 <span data-ttu-id="f7e30-107">**[谓词]**</span><span class="sxs-lookup"><span data-stu-id="f7e30-107">**[Verbs]**</span></span>
  
 <span data-ttu-id="f7e30-108">**Verb1**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f7e30-108">**Verb1** =  _string_</span></span>
  
<span data-ttu-id="f7e30-109">下面是 [ **谓词] 部分** 的示例。</span><span class="sxs-lookup"><span data-stu-id="f7e30-109">Following is an example of a **[Verbs]** section.</span></span> 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

<span data-ttu-id="f7e30-110">每个动词在单独的 [谓词中 **定义。**</span><span class="sxs-lookup"><span data-stu-id="f7e30-110">Each verb is defined in a separate **[Verb.**</span></span> <span data-ttu-id="f7e30-111">_string_ **]** section.</span><span class="sxs-lookup"><span data-stu-id="f7e30-111">_string_ **]** section.</span></span> <span data-ttu-id="f7e30-112">一 **个 [谓词。**</span><span class="sxs-lookup"><span data-stu-id="f7e30-112">A **[Verb.**</span></span> <span data-ttu-id="f7e30-113">_string_ **]** 节描述表单提供的单个动词。</span><span class="sxs-lookup"><span data-stu-id="f7e30-113">_string_ **]** section describes a single verb offered by the form.</span></span> <span data-ttu-id="f7e30-114">[ **谓词中的 DisplayName** **条目。**</span><span class="sxs-lookup"><span data-stu-id="f7e30-114">The **DisplayName** entry in a **[Verb.**</span></span> <span data-ttu-id="f7e30-115">_string_ **]** 节指定用户界面中显示的命令名称。</span><span class="sxs-lookup"><span data-stu-id="f7e30-115">_string_ **]** section specifies the command name displayed in the user interface.</span></span> <span data-ttu-id="f7e30-116">Code **条目** 对应于 [IMAPIForm：:D oVerb 方法中传递](imapiform-doverb.md) 的动词编号。</span><span class="sxs-lookup"><span data-stu-id="f7e30-116">The **Code** entry corresponds to the verb number passed in the [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> <span data-ttu-id="f7e30-117">**[Verb.**</span><span class="sxs-lookup"><span data-stu-id="f7e30-117">The syntax for the **[Verb.**</span></span> <span data-ttu-id="f7e30-118">_string_ **]** section is：</span><span class="sxs-lookup"><span data-stu-id="f7e30-118">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="f7e30-119">**[动词。**</span><span class="sxs-lookup"><span data-stu-id="f7e30-119">**[Verb.**</span></span> <span data-ttu-id="f7e30-120">_string_ **]**</span><span class="sxs-lookup"><span data-stu-id="f7e30-120">_string_ **]**</span></span>
  
 <span data-ttu-id="f7e30-121">**DisplayName**  =  _显示的字符串_</span><span class="sxs-lookup"><span data-stu-id="f7e30-121">**DisplayName** =  _displayed string_</span></span>
  
 <span data-ttu-id="f7e30-122">**代码**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f7e30-122">**Code** =  _integer_</span></span>
  
 <span data-ttu-id="f7e30-123">**Flags**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f7e30-123">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="f7e30-124">**Attribs**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f7e30-124">**Attribs** =  _integer_</span></span>
  
<span data-ttu-id="f7e30-125">下面是一个 **[谓词示例。**</span><span class="sxs-lookup"><span data-stu-id="f7e30-125">Following is an example of a **[Verb.**</span></span> <span data-ttu-id="f7e30-126">_string_ **]** section.</span><span class="sxs-lookup"><span data-stu-id="f7e30-126">_string_ **]** section.</span></span> 
  
```cpp
[Verb.1]
DisplayName=Reply
code=1
Flags=0
Attribs=2
[Verb.2]
DisplayName=Delete
Code=2
Flags=0
Attribs=2

```

<span data-ttu-id="f7e30-127">本节中列出的谓词由客户端使用 [IMAPIFormInfo：：CalcVerbSet](imapiforminfo-calcverbset.md)方法检索。</span><span class="sxs-lookup"><span data-stu-id="f7e30-127">Verbs listed in this section are retrieved by a client using the [IMAPIFormInfo::CalcVerbSet method](imapiforminfo-calcverbset.md).</span></span> <span data-ttu-id="f7e30-128">通过调用表单的 [IMAPIForm：:D oVerb](imapiform-doverb.md) 方法，并传递给它要执行谓词的代码编号，可激活动词。</span><span class="sxs-lookup"><span data-stu-id="f7e30-128">Verbs are activated by calling the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method and passing it the code number of the verb to be performed.</span></span> 
  

