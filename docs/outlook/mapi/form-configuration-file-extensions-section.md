---
title: 表单配置文件 [扩展名] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4817e446-982d-491c-abcf-cc888a771afa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 459c5f5a34421583141028cd9accad5e242d31ad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573556"
---
# <a name="form-configuration-file-extensions-section"></a><span data-ttu-id="18268-103">表单配置文件 [扩展名] 部分</span><span class="sxs-lookup"><span data-stu-id="18268-103">Form Configuration File [Extensions] Section</span></span>

  
  
<span data-ttu-id="18268-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="18268-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="18268-105">**[扩展]** 节列出了窗体，通常命名的属性集的扩展的属性，它们是超出基本窗体配置文件的 **[描述]** 节中列出的任何属性。</span><span class="sxs-lookup"><span data-stu-id="18268-105">The **[Extensions]** section lists the extended attributes of the form, typically a named property set, which are any attributes beyond the basic ones listed in the **[Description]** section of the form configuration file.</span></span> <span data-ttu-id="18268-106">扩展的属性是使用较高的位属性标记中设置**GetProps** **IMAPIFormInfo**对象的方法的调用返回的属性。</span><span class="sxs-lookup"><span data-stu-id="18268-106">Extended attributes are properties returned from calls to the **GetProps** method of the **IMAPIFormInfo** object with the high bit set in the property tag.</span></span> <span data-ttu-id="18268-107">如果有，通过检索这些标记，客户端应用程序可以确定窗体的扩展的属性。</span><span class="sxs-lookup"><span data-stu-id="18268-107">Client applications can determine a form's extended attributes, if any, by retrieving these tags.</span></span> <span data-ttu-id="18268-108">这样，客户端调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法，传递中窗体的属性的名称，并调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法以获取属性。</span><span class="sxs-lookup"><span data-stu-id="18268-108">To do so, clients call the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method, passing in the names of the form's properties and call the [IMAPIProp::GetProps](imapiprop-getprops.md) method to get the properties.</span></span> 
  
 <span data-ttu-id="18268-109">**[扩展]**</span><span class="sxs-lookup"><span data-stu-id="18268-109">**[Extensions]**</span></span>
  
 <span data-ttu-id="18268-110">**扩展。**</span><span class="sxs-lookup"><span data-stu-id="18268-110">**Extension.**</span></span> <span data-ttu-id="18268-111">_string1_ =  _string2_</span><span class="sxs-lookup"><span data-stu-id="18268-111">_string1_ =  _string2_</span></span>
  
<span data-ttu-id="18268-112">每个扩展名属性部分定义一个使用 MAPI 命名属性的语法的扩展特性。</span><span class="sxs-lookup"><span data-stu-id="18268-112">Each extension property section defines one extension attribute using the MAPI named property syntax.</span></span> <span data-ttu-id="18268-113">属性类型必须是 PT_LONG 或 PT_STRING8。</span><span class="sxs-lookup"><span data-stu-id="18268-113">The property type must be either PT_LONG or PT_STRING8.</span></span> <span data-ttu-id="18268-114">不支持包含名为的字符串的属性集。</span><span class="sxs-lookup"><span data-stu-id="18268-114">Property sets that contains named strings are not supported.</span></span> <span data-ttu-id="18268-115">**[扩展]** 节的格式为：</span><span class="sxs-lookup"><span data-stu-id="18268-115">The format of the **[Extension]** section is:</span></span> 
  
 <span data-ttu-id="18268-116">**[扩展名。**</span><span class="sxs-lookup"><span data-stu-id="18268-116">**[Extension.**</span></span> <span data-ttu-id="18268-117">_string2_**]**</span><span class="sxs-lookup"><span data-stu-id="18268-117">_string2_ **]**</span></span>
  
 <span data-ttu-id="18268-118">**类型** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="18268-118">**Type** =  _integer_</span></span>
  
 <span data-ttu-id="18268-119">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="18268-119">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="18268-120">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="18268-120">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="18268-121">**值** =  _字符串_ |  _整数_</span><span class="sxs-lookup"><span data-stu-id="18268-121">**Value** =  _string_ |  _integer_</span></span>
  
<span data-ttu-id="18268-122">**[扩展]** 一节和后续相关的部分的示例所示关注。</span><span class="sxs-lookup"><span data-stu-id="18268-122">An example of an **[Extensions]** section and a subsequent related section is shown following.</span></span> 
  
```
[Extensions]
Extension.A = 1
[Extension.1]
Type = 30
NmidPropset = {00020D0C-0000-0000-C000-000000000046}
NmidInteger = 1
Value = 11220000

```


