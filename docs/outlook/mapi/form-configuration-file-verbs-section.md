---
title: 表单配置文件 [谓词] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7e1f371-9e9a-4bec-a0b3-87753a16f5e0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6a06283e3eb072e1f502d0b1bd303ce9f0733578
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583972"
---
# <a name="form-configuration-file-verbs-section"></a><span data-ttu-id="24e38-103">表单配置文件 [谓词] 部分</span><span class="sxs-lookup"><span data-stu-id="24e38-103">Form Configuration File [Verbs] Section</span></span>

  
  
<span data-ttu-id="24e38-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24e38-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24e38-105">**[谓词]** 节列出了支持表单谓词的完整集合。</span><span class="sxs-lookup"><span data-stu-id="24e38-105">The **[Verbs]** section lists the complete set of verbs supported by the form.</span></span> <span data-ttu-id="24e38-106">**[谓词]** 节的格式为：</span><span class="sxs-lookup"><span data-stu-id="24e38-106">The format of the **[Verbs]** section is:</span></span> 
  
 <span data-ttu-id="24e38-107">**[谓词]**</span><span class="sxs-lookup"><span data-stu-id="24e38-107">**[Verbs]**</span></span>
  
 <span data-ttu-id="24e38-108">**Verb1** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="24e38-108">**Verb1** =  _string_</span></span>
  
<span data-ttu-id="24e38-109">以下是 **[谓词]** 部分的示例。</span><span class="sxs-lookup"><span data-stu-id="24e38-109">Following is an example of a **[Verbs]** section.</span></span> 
  
```cpp
[Verbs]
Verb1=1
Verb2=2

```

<span data-ttu-id="24e38-110">每个动作定义在单独 **[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-110">Each verb is defined in a separate **[Verb.**</span></span> <span data-ttu-id="24e38-111">_字符串_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="24e38-111">_string_ **]** section.</span></span> <span data-ttu-id="24e38-112">A **[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-112">A **[Verb.**</span></span> <span data-ttu-id="24e38-113">_字符串_**]** 部分介绍单个动词形式提供。</span><span class="sxs-lookup"><span data-stu-id="24e38-113">_string_ **]** section describes a single verb offered by the form.</span></span> <span data-ttu-id="24e38-114">中的**DisplayName**条目 **[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-114">The **DisplayName** entry in a **[Verb.**</span></span> <span data-ttu-id="24e38-115">_字符串_**]** 节指定在用户界面中显示的命令名称。</span><span class="sxs-lookup"><span data-stu-id="24e38-115">_string_ **]** section specifies the command name displayed in the user interface.</span></span> <span data-ttu-id="24e38-116">[IMAPIForm::DoVerb](imapiform-doverb.md)方法中传递的动词编号相对应的**代码**条目。</span><span class="sxs-lookup"><span data-stu-id="24e38-116">The **Code** entry corresponds to the verb number passed in the [IMAPIForm::DoVerb](imapiform-doverb.md) method.</span></span> <span data-ttu-id="24e38-117">语法为 **[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-117">The syntax for the **[Verb.**</span></span> <span data-ttu-id="24e38-118">_字符串_**]** 部分是：</span><span class="sxs-lookup"><span data-stu-id="24e38-118">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="24e38-119">**[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-119">**[Verb.**</span></span> <span data-ttu-id="24e38-120">_字符串_**]**</span><span class="sxs-lookup"><span data-stu-id="24e38-120">_string_ **]**</span></span>
  
 <span data-ttu-id="24e38-121">**DisplayName** =  _显示字符串_</span><span class="sxs-lookup"><span data-stu-id="24e38-121">**DisplayName** =  _displayed string_</span></span>
  
 <span data-ttu-id="24e38-122">**代码** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="24e38-122">**Code** =  _integer_</span></span>
  
 <span data-ttu-id="24e38-123">**Flags** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="24e38-123">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="24e38-124">**Attribs** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="24e38-124">**Attribs** =  _integer_</span></span>
  
<span data-ttu-id="24e38-125">下面是示例 **[动词。**</span><span class="sxs-lookup"><span data-stu-id="24e38-125">Following is an example of a **[Verb.**</span></span> <span data-ttu-id="24e38-126">_字符串_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="24e38-126">_string_ **]** section.</span></span> 
  
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

<span data-ttu-id="24e38-127">本节中列出的动作将检索客户端使用[IMAPIFormInfo::CalcVerbSet 方法](imapiforminfo-calcverbset.md)。</span><span class="sxs-lookup"><span data-stu-id="24e38-127">Verbs listed in this section are retrieved by a client using the [IMAPIFormInfo::CalcVerbSet method](imapiforminfo-calcverbset.md).</span></span> <span data-ttu-id="24e38-128">通过调用窗体的[IMAPIForm::DoVerb](imapiform-doverb.md)方法并将其传递要执行的动作代码号激活动词。</span><span class="sxs-lookup"><span data-stu-id="24e38-128">Verbs are activated by calling the form's [IMAPIForm::DoVerb](imapiform-doverb.md) method and passing it the code number of the verb to be performed.</span></span> 
  

