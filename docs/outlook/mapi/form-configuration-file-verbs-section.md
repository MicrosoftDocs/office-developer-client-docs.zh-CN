---
title: 表单配置文件 [谓词] 部分
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
# <a name="form-configuration-file-verbs-section"></a><span data-ttu-id="8a3fa-103">表单配置文件 [谓词] 部分</span><span class="sxs-lookup"><span data-stu-id="8a3fa-103">Form Configuration File [Verbs] Section</span></span>

  
  
<span data-ttu-id="8a3fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8a3fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8a3fa-105">**[谓词]** 部分列出了窗体支持的完整谓词集。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-105">The **[Verbs]** section lists the complete set of verbs supported by the form.</span></span> <span data-ttu-id="8a3fa-106">**[谓词]** 部分的格式为:</span><span class="sxs-lookup"><span data-stu-id="8a3fa-106">The format of the **[Verbs]** section is:</span></span> 
  
 <span data-ttu-id="8a3fa-107">**谓词**</span><span class="sxs-lookup"><span data-stu-id="8a3fa-107">**[Verbs]**</span></span>
  
 <span data-ttu-id="8a3fa-108">**Verb1** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="8a3fa-108">**Verb1** =  _string_</span></span>
  
<span data-ttu-id="8a3fa-109">以下是 **[谓词]** 部分的一个示例。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-109">Following is an example of a **[Verbs]** section.</span></span> 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

<span data-ttu-id="8a3fa-110">每个谓词都在一个单独的 **[谓词**中定义。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-110">Each verb is defined in a separate **[Verb.**</span></span> <span data-ttu-id="8a3fa-111">_string_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-111">_string_ **]** section.</span></span> <span data-ttu-id="8a3fa-112">A **[谓词。**</span><span class="sxs-lookup"><span data-stu-id="8a3fa-112">A **[Verb.**</span></span> <span data-ttu-id="8a3fa-113">_string_**]** 部分介绍由窗体提供的单个谓词。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-113">_string_ **]** section describes a single verb offered by the form.</span></span> <span data-ttu-id="8a3fa-114">**[谓词**] 中的**DisplayName**项。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-114">The **DisplayName** entry in a **[Verb.**</span></span> <span data-ttu-id="8a3fa-115">_string_**]** 部分指定在用户界面中显示的命令名称。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-115">_string_ **]** section specifies the command name displayed in the user interface.</span></span> <span data-ttu-id="8a3fa-116">**代码**条目对应于[IMAPIForm::D overb](imapiform-doverb.md)方法中传递的动词编号。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-116">The **Code** entry corresponds to the verb number passed in the [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> <span data-ttu-id="8a3fa-117">**[谓词**] 的语法。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-117">The syntax for the **[Verb.**</span></span> <span data-ttu-id="8a3fa-118">_string_**]** 部分为:</span><span class="sxs-lookup"><span data-stu-id="8a3fa-118">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="8a3fa-119">**动词.**</span><span class="sxs-lookup"><span data-stu-id="8a3fa-119">**[Verb.**</span></span> <span data-ttu-id="8a3fa-120">_string_**]**</span><span class="sxs-lookup"><span data-stu-id="8a3fa-120">_string_ **]**</span></span>
  
 <span data-ttu-id="8a3fa-121">**DisplayName** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="8a3fa-121">**DisplayName** =  _displayed string_</span></span>
  
 <span data-ttu-id="8a3fa-122">**代码** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="8a3fa-122">**Code** =  _integer_</span></span>
  
 <span data-ttu-id="8a3fa-123">**Flags** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="8a3fa-123">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="8a3fa-124">**Attribs** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="8a3fa-124">**Attribs** =  _integer_</span></span>
  
<span data-ttu-id="8a3fa-125">下面是一个 **[谓词**的示例。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-125">Following is an example of a **[Verb.**</span></span> <span data-ttu-id="8a3fa-126">_string_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-126">_string_ **]** section.</span></span> 
  
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

<span data-ttu-id="8a3fa-127">客户端使用[IMAPIFormInfo:: CalcVerbSet 方法](imapiforminfo-calcverbset.md)检索本节中列出的谓词。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-127">Verbs listed in this section are retrieved by a client using the [IMAPIFormInfo::CalcVerbSet method](imapiforminfo-calcverbset.md).</span></span> <span data-ttu-id="8a3fa-128">通过调用窗体的[IMAPIForm::D overb](imapiform-doverb.md)方法并向其传递要执行的谓词的代码编号来激活谓词。</span><span class="sxs-lookup"><span data-stu-id="8a3fa-128">Verbs are activated by calling the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method and passing it the code number of the verb to be performed.</span></span> 
  

