---
title: SMAPIFormPropEnumVal
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormPropEnumVal
api_type:
- COM
ms.assetid: 694d40e9-cff2-435e-ad90-446044c306d2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2c49a17389a9bfc998f892e0becf96dca4cd773f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578715"
---
# <a name="smapiformpropenumval"></a><span data-ttu-id="c4b87-103">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="c4b87-103">SMAPIFormPropEnumVal</span></span>

  
  
<span data-ttu-id="c4b87-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4b87-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4b87-105">将枚举的整数值映射到该值的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c4b87-105">Maps an enumerated integer value to a display name for that value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c4b87-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c4b87-106">Header file:</span></span>  <br/> |<span data-ttu-id="c4b87-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="c4b87-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a><span data-ttu-id="c4b87-108">Members</span><span class="sxs-lookup"><span data-stu-id="c4b87-108">Members</span></span>

 <span data-ttu-id="c4b87-109">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="c4b87-109">**pszDisplayName**</span></span>
  
> <span data-ttu-id="c4b87-110">包含**nVal**成员中指定的值的显示名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="c4b87-110">String that contains the display name for the value specified in the **nVal** member.</span></span> 
    
 <span data-ttu-id="c4b87-111">**nVal**</span><span class="sxs-lookup"><span data-stu-id="c4b87-111">**nVal**</span></span>
  
> <span data-ttu-id="c4b87-112">显示名称指向**pszDisplayName**成员的一个枚举值。</span><span class="sxs-lookup"><span data-stu-id="c4b87-112">An enumeration value for the display name pointed to by the **pszDisplayName** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c4b87-113">注解</span><span class="sxs-lookup"><span data-stu-id="c4b87-113">Remarks</span></span>

<span data-ttu-id="c4b87-114">当用户选择窗体中的显示名称时，使用该[IMAPIProp](imapipropiunknown.md)接口实现与表单关联的存储该名称的相应的枚举值。</span><span class="sxs-lookup"><span data-stu-id="c4b87-114">When a user selects a display name from a form, the name's corresponding enumeration value is stored by using the [IMAPIProp](imapipropiunknown.md) interface implementation that is associated with the form.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c4b87-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b87-115">See also</span></span>



[<span data-ttu-id="c4b87-116">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="c4b87-116">SMAPIFormProp</span></span>](smapiformprop.md)
  
[<span data-ttu-id="c4b87-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c4b87-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="c4b87-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c4b87-118">MAPI Structures</span></span>](mapi-structures.md)

