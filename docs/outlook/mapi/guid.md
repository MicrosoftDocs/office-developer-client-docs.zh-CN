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
ms.openlocfilehash: 94bafdf0ca84fa31a7df2f022265d5d5d1a99a37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577693"
---
# <a name="guid"></a><span data-ttu-id="b3430-103">GUID</span><span class="sxs-lookup"><span data-stu-id="b3430-103">GUID</span></span>

  
  
<span data-ttu-id="b3430-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3430-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3430-105">介绍的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="b3430-105">Describes a globally unique identifier (GUID).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b3430-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b3430-106">Header file:</span></span>  <br/> |<span data-ttu-id="b3430-107">Mapiguid.h</span><span class="sxs-lookup"><span data-stu-id="b3430-107">Mapiguid.h</span></span>  <br/> |
   
```cpp
typedef struct _GUID
{
  unsigned long Data1;
  unsigned short Data2;
  unsigned short Data3;
  unsigned char Data4[8];
} GUID;

```

## <a name="members"></a><span data-ttu-id="b3430-108">Members</span><span class="sxs-lookup"><span data-stu-id="b3430-108">Members</span></span>

 <span data-ttu-id="b3430-109">**Data1**</span><span class="sxs-lookup"><span data-stu-id="b3430-109">**Data1**</span></span>
  
> <span data-ttu-id="b3430-110">无符号的长整型数据值。</span><span class="sxs-lookup"><span data-stu-id="b3430-110">An unsigned long integer data value.</span></span>
    
 <span data-ttu-id="b3430-111">**Data2**</span><span class="sxs-lookup"><span data-stu-id="b3430-111">**Data2**</span></span>
  
> <span data-ttu-id="b3430-112">无符号短整数数据值。</span><span class="sxs-lookup"><span data-stu-id="b3430-112">An unsigned short integer data value.</span></span>
    
 <span data-ttu-id="b3430-113">**Data3**</span><span class="sxs-lookup"><span data-stu-id="b3430-113">**Data3**</span></span>
  
> <span data-ttu-id="b3430-114">无符号短整数数据值。</span><span class="sxs-lookup"><span data-stu-id="b3430-114">An unsigned short integer data value.</span></span>
    
 <span data-ttu-id="b3430-115">**Data4**</span><span class="sxs-lookup"><span data-stu-id="b3430-115">**Data4**</span></span>
  
> <span data-ttu-id="b3430-116">无符号字符数组。</span><span class="sxs-lookup"><span data-stu-id="b3430-116">An array of unsigned characters.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b3430-117">注解</span><span class="sxs-lookup"><span data-stu-id="b3430-117">Remarks</span></span>

 <span data-ttu-id="b3430-118">**GUID**结构中将使用 MAPI，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b3430-118">**GUID** structures are used in MAPI as follows:</span></span> 
  
- <span data-ttu-id="b3430-119">[MAPIUID](mapiuid.md)结构中的唯一标识服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b3430-119">In the [MAPIUID](mapiuid.md) structures that uniquely identify service providers.</span></span> 
    
- <span data-ttu-id="b3430-120">接口标识符。</span><span class="sxs-lookup"><span data-stu-id="b3430-120">For interface identifiers.</span></span>
    
- <span data-ttu-id="b3430-121">属性中设置命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b3430-121">In the property set names of named properties.</span></span> 
    
<span data-ttu-id="b3430-122">消息存储和地址簿提供程序生成的**GUID**结构使用其**MAPIUID**结构中。</span><span class="sxs-lookup"><span data-stu-id="b3430-122">Message store and address book providers generate a **GUID** structure to use in their **MAPIUID** structure.</span></span> <span data-ttu-id="b3430-123">通过将生成**MAPIUID**传递给[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)，这些服务提供商告知 MAPI，其唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b3430-123">By passing the resulting **MAPIUID** to [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md), these service providers inform MAPI of their unique identifier.</span></span>
  
<span data-ttu-id="b3430-124">另外，他们的 Microsoft 远程过程调用 (RPC) 和对象描述语言 (ODL) 实现中使用。</span><span class="sxs-lookup"><span data-stu-id="b3430-124">Also, they are used in the implementation of Microsoft Remote Procedure Call (RPC) and the Object Description Language (ODL).</span></span> <span data-ttu-id="b3430-125">有关这些使用的详细信息，请参阅*Microsoft RPC 程序员指南和参考 （英文）*、 *OLE 程序员参考*和*内部 OLE*，*第二版*。</span><span class="sxs-lookup"><span data-stu-id="b3430-125">For more information about these uses, see the  *Microsoft RPC Programmer's Guide and Reference*, *OLE Programmer's Reference*  ,and  *Inside OLE*, *Second Edition*  .</span></span> 
  
<span data-ttu-id="b3430-126">**GUID**结构是*Win32 程序员参考*中定义的。</span><span class="sxs-lookup"><span data-stu-id="b3430-126">The **GUID** structure is defined in the  *Win32 Programmer's Reference*  .</span></span> <span data-ttu-id="b3430-127">MAPI 头文件 Mapiguid.h 中定义的**GUID**结构 MAPI 内使用的特定值。</span><span class="sxs-lookup"><span data-stu-id="b3430-127">Specific values for **GUID** structures that are used within MAPI are defined in the MAPI header file Mapiguid.h.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b3430-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3430-128">See also</span></span>



[<span data-ttu-id="b3430-129">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="b3430-129">MAPIUID</span></span>](mapiuid.md)


[<span data-ttu-id="b3430-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b3430-130">MAPI Structures</span></span>](mapi-structures.md)

