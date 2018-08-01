---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此数据类型变量包含的一个属性，它是 variant 数据类型的值。
ms.openlocfilehash: c85af4bd4fefffb4fadf671bb7cf5b7f072d5e95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774172"
---
# <a name="acctvariant"></a><span data-ttu-id="f62a0-103">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="f62a0-103">ACCT_VARIANT</span></span>

<span data-ttu-id="f62a0-104">此数据类型变量包含的一个属性，它是 variant 数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="f62a0-104">A variable of this data type holds the value of a property, which is of a variant data type.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f62a0-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="f62a0-105">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="f62a0-106">Members</span><span class="sxs-lookup"><span data-stu-id="f62a0-106">Members</span></span>

<span data-ttu-id="f62a0-107">_dwType_</span><span class="sxs-lookup"><span data-stu-id="f62a0-107">_dwType_</span></span>
  
> <span data-ttu-id="f62a0-108">Variant 类型：</span><span class="sxs-lookup"><span data-stu-id="f62a0-108">Type of variant:</span></span>
    
    - <span data-ttu-id="f62a0-109">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f62a0-109">PT_LONG</span></span>
    
    - <span data-ttu-id="f62a0-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f62a0-110">PT_UNICODE</span></span>
    
    - <span data-ttu-id="f62a0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f62a0-111">PT_BINARY</span></span>
    
<span data-ttu-id="f62a0-112">_数据仓库_</span><span class="sxs-lookup"><span data-stu-id="f62a0-112">_dw_</span></span>
  
> <span data-ttu-id="f62a0-113">Variant 的 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="f62a0-113">DWORD value of variant.</span></span>
    
<span data-ttu-id="f62a0-114">_pwsz_</span><span class="sxs-lookup"><span data-stu-id="f62a0-114">_pwsz_</span></span>
  
> <span data-ttu-id="f62a0-115">Variant 类型的值的字符串值。</span><span class="sxs-lookup"><span data-stu-id="f62a0-115">String value of variant.</span></span>
    
<span data-ttu-id="f62a0-116">_回收站_</span><span class="sxs-lookup"><span data-stu-id="f62a0-116">_bin_</span></span>
  
> <span data-ttu-id="f62a0-117">二进制值的 variant。</span><span class="sxs-lookup"><span data-stu-id="f62a0-117">Binary value of the variant.</span></span>
    

