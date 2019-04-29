---
title: 表单配置文件 [extension] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4817e446-982d-491c-abcf-cc888a771afa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 96682dd2bdfedc42ea13c6985cb834f0adffd4df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423753"
---
# <a name="form-configuration-file-extensions-section"></a><span data-ttu-id="58b85-103">表单配置文件 [extension] 部分</span><span class="sxs-lookup"><span data-stu-id="58b85-103">Form Configuration File [Extensions] Section</span></span>

  
  
<span data-ttu-id="58b85-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58b85-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58b85-105">**[extension]** 部分列出了窗体的扩展属性 (通常是一个命名属性集), 它是表单配置文件的 **[Description]** 部分中列出的基本属性以外的任何属性。</span><span class="sxs-lookup"><span data-stu-id="58b85-105">The **[Extensions]** section lists the extended attributes of the form, typically a named property set, which are any attributes beyond the basic ones listed in the **[Description]** section of the form configuration file.</span></span> <span data-ttu-id="58b85-106">扩展属性是通过调用**IMAPIFormInfo**对象的**GetProps**方法返回的属性, 该属性标记中设置了高位。</span><span class="sxs-lookup"><span data-stu-id="58b85-106">Extended attributes are properties returned from calls to the **GetProps** method of the **IMAPIFormInfo** object with the high bit set in the property tag.</span></span> <span data-ttu-id="58b85-107">客户端应用程序可以通过检索这些标记来确定表单的扩展属性 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="58b85-107">Client applications can determine a form's extended attributes, if any, by retrieving these tags.</span></span> <span data-ttu-id="58b85-108">为此, 客户端调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法, 传入窗体属性的名称并调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以获取属性。</span><span class="sxs-lookup"><span data-stu-id="58b85-108">To do so, clients call the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method, passing in the names of the form's properties and call the [IMAPIProp::GetProps](imapiprop-getprops.md) method to get the properties.</span></span> 
  
 <span data-ttu-id="58b85-109">**长度**</span><span class="sxs-lookup"><span data-stu-id="58b85-109">**[Extensions]**</span></span>
  
 <span data-ttu-id="58b85-110">**扩展.**</span><span class="sxs-lookup"><span data-stu-id="58b85-110">**Extension.**</span></span> <span data-ttu-id="58b85-111">_string1_ =  _string2_</span><span class="sxs-lookup"><span data-stu-id="58b85-111">_string1_ =  _string2_</span></span>
  
<span data-ttu-id="58b85-112">每个扩展属性部分使用 MAPI 命名属性语法定义一个扩展属性。</span><span class="sxs-lookup"><span data-stu-id="58b85-112">Each extension property section defines one extension attribute using the MAPI named property syntax.</span></span> <span data-ttu-id="58b85-113">属性类型必须是 PT_LONG 或 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="58b85-113">The property type must be either PT_LONG or PT_STRING8.</span></span> <span data-ttu-id="58b85-114">不支持包含命名字符串的属性集。</span><span class="sxs-lookup"><span data-stu-id="58b85-114">Property sets that contains named strings are not supported.</span></span> <span data-ttu-id="58b85-115">**[Extension]** 部分的格式为:</span><span class="sxs-lookup"><span data-stu-id="58b85-115">The format of the **[Extension]** section is:</span></span> 
  
 <span data-ttu-id="58b85-116">**扩展.**</span><span class="sxs-lookup"><span data-stu-id="58b85-116">**[Extension.**</span></span> <span data-ttu-id="58b85-117">_string2_**]**</span><span class="sxs-lookup"><span data-stu-id="58b85-117">_string2_ **]**</span></span>
  
 <span data-ttu-id="58b85-118">**类型** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="58b85-118">**Type** =  _integer_</span></span>
  
 <span data-ttu-id="58b85-119">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="58b85-119">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="58b85-120">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="58b85-120">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="58b85-121">**值** =  __ 字符串 |  _integer_</span><span class="sxs-lookup"><span data-stu-id="58b85-121">**Value** =  _string_ |  _integer_</span></span>
  
<span data-ttu-id="58b85-122">下面显示了一个 **[extension]** 部分和一个随后相关的部分的示例。</span><span class="sxs-lookup"><span data-stu-id="58b85-122">An example of an **[Extensions]** section and a subsequent related section is shown following.</span></span> 
  
```
[Extensions]
Extension.A = 1
[Extension.1]
Type = 30
NmidPropset = {00020D0C-0000-0000-C000-000000000046}
NmidInteger = 1
Value = 11220000

```


