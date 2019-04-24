---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此数据类型的变量包含一个 variant 数据类型的属性值。
ms.openlocfilehash: 124cfaef40e63d60e2e9c6681884bfb57a043dde
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316917"
---
# <a name="acctvariant"></a><span data-ttu-id="cb981-103">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="cb981-103">ACCT_VARIANT</span></span>

<span data-ttu-id="cb981-104">此数据类型的变量包含一个 variant 数据类型的属性值。</span><span class="sxs-lookup"><span data-stu-id="cb981-104">A variable of this data type holds the value of a property, which is of a variant data type.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="cb981-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="cb981-105">Quick info</span></span>

```cpp
typedef struct 
    { 
        DWORD dwType; 
        union  
            { 
            DWORD dw; 
            WCHAR *pwsz; 
            ACCT_BIN bin; 
            } Val; 
    } ACCT_VARIANT; 

```

## <a name="members"></a><span data-ttu-id="cb981-106">成员</span><span class="sxs-lookup"><span data-stu-id="cb981-106">Members</span></span>

<span data-ttu-id="cb981-107">_dwType_</span><span class="sxs-lookup"><span data-stu-id="cb981-107">_dwType_</span></span>
  
> <span data-ttu-id="cb981-108">变量类型:</span><span class="sxs-lookup"><span data-stu-id="cb981-108">Type of variant:</span></span>
    
    - <span data-ttu-id="cb981-109">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cb981-109">PT_LONG</span></span>
    
    - <span data-ttu-id="cb981-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cb981-110">PT_UNICODE</span></span>
    
    - <span data-ttu-id="cb981-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cb981-111">PT_BINARY</span></span>
    
<span data-ttu-id="cb981-112">_仓库_</span><span class="sxs-lookup"><span data-stu-id="cb981-112">_dw_</span></span>
  
> <span data-ttu-id="cb981-113">variant 的 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="cb981-113">DWORD value of variant.</span></span>
    
<span data-ttu-id="cb981-114">_pwsz_</span><span class="sxs-lookup"><span data-stu-id="cb981-114">_pwsz_</span></span>
  
> <span data-ttu-id="cb981-115">variant 的字符串值。</span><span class="sxs-lookup"><span data-stu-id="cb981-115">String value of variant.</span></span>
    
<span data-ttu-id="cb981-116">_区间_</span><span class="sxs-lookup"><span data-stu-id="cb981-116">_bin_</span></span>
  
> <span data-ttu-id="cb981-117">变量的二进制值。</span><span class="sxs-lookup"><span data-stu-id="cb981-117">Binary value of the variant.</span></span>
    

