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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435409"
---
# <a name="smapiformpropenumval"></a><span data-ttu-id="20972-103">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="20972-103">SMAPIFormPropEnumVal</span></span>

  
  
<span data-ttu-id="20972-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20972-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20972-105">地图枚举的整数值显示名称该值的整数值。</span><span class="sxs-lookup"><span data-stu-id="20972-105">Maps an enumerated integer value to a display name for that value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="20972-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="20972-106">Header file:</span></span>  <br/> |<span data-ttu-id="20972-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="20972-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a><span data-ttu-id="20972-108">Members</span><span class="sxs-lookup"><span data-stu-id="20972-108">Members</span></span>

 <span data-ttu-id="20972-109">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="20972-109">**pszDisplayName**</span></span>
  
> <span data-ttu-id="20972-110">字符串，包含显示名称 **nVal** 成员中指定的值的字符串。</span><span class="sxs-lookup"><span data-stu-id="20972-110">String that contains the display name for the value specified in the **nVal** member.</span></span> 
    
 <span data-ttu-id="20972-111">**nVal**</span><span class="sxs-lookup"><span data-stu-id="20972-111">**nVal**</span></span>
  
> <span data-ttu-id="20972-112">**pszDisplayName** 显示名称指向的枚举值。</span><span class="sxs-lookup"><span data-stu-id="20972-112">An enumeration value for the display name pointed to by the **pszDisplayName** member.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="20972-113">备注</span><span class="sxs-lookup"><span data-stu-id="20972-113">Remarks</span></span>

<span data-ttu-id="20972-114">当用户从表单显示名称时，会使用与表单关联的 [IMAPIProp](imapipropiunknown.md) 接口实现来存储名称的相应枚举值。</span><span class="sxs-lookup"><span data-stu-id="20972-114">When a user selects a display name from a form, the name's corresponding enumeration value is stored by using the [IMAPIProp](imapipropiunknown.md) interface implementation that is associated with the form.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="20972-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20972-115">See also</span></span>



[<span data-ttu-id="20972-116">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="20972-116">SMAPIFormProp</span></span>](smapiformprop.md)
  
[<span data-ttu-id="20972-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="20972-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="20972-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="20972-118">MAPI Structures</span></span>](mapi-structures.md)

