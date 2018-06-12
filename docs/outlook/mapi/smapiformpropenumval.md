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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bae750e7e940bc1417b3d225c9c81129e9da77b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778823"
---
# <a name="smapiformpropenumval"></a><span data-ttu-id="b2c6b-103">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="b2c6b-103">SMAPIFormPropEnumVal</span></span>

  
  
<span data-ttu-id="b2c6b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b2c6b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b2c6b-105">将枚举的整数值映射到该值的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b2c6b-105">Maps an enumerated integer value to a display name for that value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b2c6b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b2c6b-106">Header file:</span></span>  <br/> |<span data-ttu-id="b2c6b-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="b2c6b-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a><span data-ttu-id="b2c6b-108">成员</span><span class="sxs-lookup"><span data-stu-id="b2c6b-108">Members</span></span>

 <span data-ttu-id="b2c6b-109">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="b2c6b-109">**pszDisplayName**</span></span>
  
> <span data-ttu-id="b2c6b-110">包含**nVal**成员中指定的值的显示名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="b2c6b-110">String that contains the display name for the value specified in the **nVal** member.</span></span> 
    
 <span data-ttu-id="b2c6b-111">**nVal**</span><span class="sxs-lookup"><span data-stu-id="b2c6b-111">**nVal**</span></span>
  
> <span data-ttu-id="b2c6b-112">显示名称指向**pszDisplayName**成员的一个枚举值。</span><span class="sxs-lookup"><span data-stu-id="b2c6b-112">An enumeration value for the display name pointed to by the **pszDisplayName** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b2c6b-113">备注</span><span class="sxs-lookup"><span data-stu-id="b2c6b-113">Remarks</span></span>

<span data-ttu-id="b2c6b-114">当用户选择窗体中的显示名称时，使用该[IMAPIProp](imapipropiunknown.md)接口实现与表单关联的存储该名称的相应的枚举值。</span><span class="sxs-lookup"><span data-stu-id="b2c6b-114">When a user selects a display name from a form, the name's corresponding enumeration value is stored by using the [IMAPIProp](imapipropiunknown.md) interface implementation that is associated with the form.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b2c6b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2c6b-115">See also</span></span>



[<span data-ttu-id="b2c6b-116">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="b2c6b-116">SMAPIFormProp</span></span>](smapiformprop.md)
  
[<span data-ttu-id="b2c6b-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="b2c6b-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="b2c6b-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b2c6b-118">MAPI Structures</span></span>](mapi-structures.md)

