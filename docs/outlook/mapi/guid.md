---
title: GUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.GUID
api_type:
- COM
ms.assetid: e3608c47-06be-4476-a6ef-060fac252387
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12c50ab5936d7fffd364c276ba07ca69d3459ae7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421583"
---
# <a name="guid"></a><span data-ttu-id="26213-103">GUID</span><span class="sxs-lookup"><span data-stu-id="26213-103">GUID</span></span>

  
  
<span data-ttu-id="26213-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26213-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26213-105">描述全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="26213-105">Describes a globally unique identifier (GUID).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="26213-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="26213-106">Header file:</span></span>  <br/> |<span data-ttu-id="26213-107">Mapiguid</span><span class="sxs-lookup"><span data-stu-id="26213-107">Mapiguid.h</span></span>  <br/> |
   
```cpp
typedef struct _GUID
{
  unsigned long Data1;
  unsigned short Data2;
  unsigned short Data3;
  unsigned char Data4[8];
} GUID;

```

## <a name="members"></a><span data-ttu-id="26213-108">Members</span><span class="sxs-lookup"><span data-stu-id="26213-108">Members</span></span>

 <span data-ttu-id="26213-109">**Data1**</span><span class="sxs-lookup"><span data-stu-id="26213-109">**Data1**</span></span>
  
> <span data-ttu-id="26213-110">无符号长整型数据值。</span><span class="sxs-lookup"><span data-stu-id="26213-110">An unsigned long integer data value.</span></span>
    
 <span data-ttu-id="26213-111">**Data2**</span><span class="sxs-lookup"><span data-stu-id="26213-111">**Data2**</span></span>
  
> <span data-ttu-id="26213-112">无符号短整型数据值。</span><span class="sxs-lookup"><span data-stu-id="26213-112">An unsigned short integer data value.</span></span>
    
 <span data-ttu-id="26213-113">**Data3**</span><span class="sxs-lookup"><span data-stu-id="26213-113">**Data3**</span></span>
  
> <span data-ttu-id="26213-114">无符号短整型数据值。</span><span class="sxs-lookup"><span data-stu-id="26213-114">An unsigned short integer data value.</span></span>
    
 <span data-ttu-id="26213-115">**Data4**</span><span class="sxs-lookup"><span data-stu-id="26213-115">**Data4**</span></span>
  
> <span data-ttu-id="26213-116">无符号字符数组。</span><span class="sxs-lookup"><span data-stu-id="26213-116">An array of unsigned characters.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26213-117">说明</span><span class="sxs-lookup"><span data-stu-id="26213-117">Remarks</span></span>

 <span data-ttu-id="26213-118">**GUID**结构在 MAPI 中使用, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="26213-118">**GUID** structures are used in MAPI as follows:</span></span> 
  
- <span data-ttu-id="26213-119">在唯一标识服务提供程序的[MAPIUID](mapiuid.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="26213-119">In the [MAPIUID](mapiuid.md) structures that uniquely identify service providers.</span></span> 
    
- <span data-ttu-id="26213-120">对于接口标识符。</span><span class="sxs-lookup"><span data-stu-id="26213-120">For interface identifiers.</span></span>
    
- <span data-ttu-id="26213-121">在命名属性的属性集名称中。</span><span class="sxs-lookup"><span data-stu-id="26213-121">In the property set names of named properties.</span></span> 
    
<span data-ttu-id="26213-122">邮件存储和通讯簿提供程序生成要在其**MAPIUID**结构中使用的**GUID**结构。</span><span class="sxs-lookup"><span data-stu-id="26213-122">Message store and address book providers generate a **GUID** structure to use in their **MAPIUID** structure.</span></span> <span data-ttu-id="26213-123">通过将生成的**MAPIUID**传递给[IMAPISupport:: SetProviderUID](imapisupport-setprovideruid.md), 这些服务提供程序会通知 MAPI 其唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="26213-123">By passing the resulting **MAPIUID** to [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md), these service providers inform MAPI of their unique identifier.</span></span>
  
<span data-ttu-id="26213-124">此外, 它们还用于 Microsoft 远程过程调用 (RPC) 和对象描述语言 (ODL) 的实现。</span><span class="sxs-lookup"><span data-stu-id="26213-124">Also, they are used in the implementation of Microsoft Remote Procedure Call (RPC) and the Object Description Language (ODL).</span></span> <span data-ttu-id="26213-125">有关这些用途的详细信息, 请参阅*Microsoft RPC 程序员指南和参考*、 *ole 程序员参考*和*内部 ole*,*第二版*。</span><span class="sxs-lookup"><span data-stu-id="26213-125">For more information about these uses, see the  *Microsoft RPC Programmer's Guide and Reference*, *OLE Programmer's Reference*  ,and  *Inside OLE*, *Second Edition*  .</span></span> 
  
<span data-ttu-id="26213-126">**GUID**结构是在*Win32 程序员参考*中定义的。</span><span class="sxs-lookup"><span data-stu-id="26213-126">The **GUID** structure is defined in the  *Win32 Programmer's Reference*  .</span></span> <span data-ttu-id="26213-127">mapi 中使用的**GUID**结构的特定值是在 mapi 头文件 Mapiguid 中定义的。</span><span class="sxs-lookup"><span data-stu-id="26213-127">Specific values for **GUID** structures that are used within MAPI are defined in the MAPI header file Mapiguid.h.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="26213-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26213-128">See also</span></span>



[<span data-ttu-id="26213-129">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="26213-129">MAPIUID</span></span>](mapiuid.md)


[<span data-ttu-id="26213-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="26213-130">MAPI Structures</span></span>](mapi-structures.md)

