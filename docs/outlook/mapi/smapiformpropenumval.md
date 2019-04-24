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
ms.openlocfilehash: 353bc574ca5987d71faf4841744de30a3d6c3f19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309490"
---
# <a name="smapiformpropenumval"></a><span data-ttu-id="fc6fa-103">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="fc6fa-103">SMAPIFormPropEnumVal</span></span>

  
  
<span data-ttu-id="fc6fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fc6fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fc6fa-105">将枚举整数值映射到该值的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fc6fa-105">Maps an enumerated integer value to a display name for that value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fc6fa-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fc6fa-106">Header file:</span></span>  <br/> |<span data-ttu-id="fc6fa-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="fc6fa-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a><span data-ttu-id="fc6fa-108">Members</span><span class="sxs-lookup"><span data-stu-id="fc6fa-108">Members</span></span>

 <span data-ttu-id="fc6fa-109">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="fc6fa-109">**pszDisplayName**</span></span>
  
> <span data-ttu-id="fc6fa-110">包含**nVal**成员中指定的值的显示名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="fc6fa-110">String that contains the display name for the value specified in the **nVal** member.</span></span> 
    
 <span data-ttu-id="fc6fa-111">**nVal**</span><span class="sxs-lookup"><span data-stu-id="fc6fa-111">**nVal**</span></span>
  
> <span data-ttu-id="fc6fa-112">由**pszDisplayName**成员指向的显示名称的枚举值。</span><span class="sxs-lookup"><span data-stu-id="fc6fa-112">An enumeration value for the display name pointed to by the **pszDisplayName** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="fc6fa-113">注解</span><span class="sxs-lookup"><span data-stu-id="fc6fa-113">Remarks</span></span>

<span data-ttu-id="fc6fa-114">当用户从窗体中选择显示名称时, 将使用与表单相关联的[IMAPIProp](imapipropiunknown.md)接口实现来存储该名称对应的枚举值。</span><span class="sxs-lookup"><span data-stu-id="fc6fa-114">When a user selects a display name from a form, the name's corresponding enumeration value is stored by using the [IMAPIProp](imapipropiunknown.md) interface implementation that is associated with the form.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fc6fa-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc6fa-115">See also</span></span>



[<span data-ttu-id="fc6fa-116">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="fc6fa-116">SMAPIFormProp</span></span>](smapiformprop.md)
  
[<span data-ttu-id="fc6fa-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="fc6fa-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="fc6fa-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="fc6fa-118">MAPI Structures</span></span>](mapi-structures.md)

