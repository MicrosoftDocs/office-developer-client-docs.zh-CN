---
title: SMessageClassArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMessageClassArray
api_type:
- COM
ms.assetid: 05f8c191-db2b-4174-8b3c-a9fdabfe6ac8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 01b42c04244d35d72dd856222b4bab543b84db45
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412693"
---
# <a name="smessageclassarray"></a><span data-ttu-id="d927e-103">SMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="d927e-103">SMessageClassArray</span></span>

  
  
<span data-ttu-id="d927e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d927e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d927e-105">包含指向邮件类字符串的指针数组。</span><span class="sxs-lookup"><span data-stu-id="d927e-105">Contains an array of pointers to message class strings.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d927e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d927e-106">Header file:</span></span>  <br/> |<span data-ttu-id="d927e-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="d927e-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="d927e-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="d927e-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="d927e-109">CbMessageClassArray</span><span class="sxs-lookup"><span data-stu-id="d927e-109">CbMessageClassArray</span></span>](cbmessageclassarray.md) <br/> |
   
```cpp
typedef struct 
{
  ULONG cValues;
  LPCSTR aMessageClass[MAPI_DIM];
} SMessageClassArray, FAR * LPSMESSAGECLASSARRAY;

```

## <a name="members"></a><span data-ttu-id="d927e-110">Members</span><span class="sxs-lookup"><span data-stu-id="d927e-110">Members</span></span>

 <span data-ttu-id="d927e-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="d927e-111">**cValues**</span></span>
  
> <span data-ttu-id="d927e-112">数组中邮件类字符串指针的计数。</span><span class="sxs-lookup"><span data-stu-id="d927e-112">Count of message class string pointers in the array.</span></span>
    
 <span data-ttu-id="d927e-113">**aMessageClass**</span><span class="sxs-lookup"><span data-stu-id="d927e-113">**aMessageClass**</span></span>
  
> <span data-ttu-id="d927e-114">指向邮件类字符串的指针数组。</span><span class="sxs-lookup"><span data-stu-id="d927e-114">Array of pointers to message class strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d927e-115">备注</span><span class="sxs-lookup"><span data-stu-id="d927e-115">Remarks</span></span>

<span data-ttu-id="d927e-116">**SMessageClassArray** 结构在下列方法中作为参数传递：</span><span class="sxs-lookup"><span data-stu-id="d927e-116">The **SMessageClassArray** structure is passed as a parameter in the following methods:</span></span> 
  
- [<span data-ttu-id="d927e-117">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="d927e-117">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [<span data-ttu-id="d927e-118">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="d927e-118">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a><span data-ttu-id="d927e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d927e-119">See also</span></span>



[<span data-ttu-id="d927e-120">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d927e-120">MAPI Structures</span></span>](mapi-structures.md)

