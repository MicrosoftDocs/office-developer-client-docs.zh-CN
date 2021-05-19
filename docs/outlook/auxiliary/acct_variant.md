---
title: ACCT_VARIANT
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4664df83-cf81-36d4-189d-4a09be371638
description: 此变量的数据类型保留属性的值，该属性值是变量数据类型。
ms.openlocfilehash: 124cfaef40e63d60e2e9c6681884bfb57a043dde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424397"
---
# <a name="acct_variant"></a><span data-ttu-id="1f85f-103">ACCT_VARIANT</span><span class="sxs-lookup"><span data-stu-id="1f85f-103">ACCT_VARIANT</span></span>

<span data-ttu-id="1f85f-104">此变量的数据类型保留属性的值，该属性值是变量数据类型。</span><span class="sxs-lookup"><span data-stu-id="1f85f-104">A variable of this data type holds the value of a property, which is of a variant data type.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="1f85f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="1f85f-105">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="1f85f-106">成员</span><span class="sxs-lookup"><span data-stu-id="1f85f-106">Members</span></span>

<span data-ttu-id="1f85f-107">_dwType_</span><span class="sxs-lookup"><span data-stu-id="1f85f-107">_dwType_</span></span>
  
> <span data-ttu-id="1f85f-108">变量类型：</span><span class="sxs-lookup"><span data-stu-id="1f85f-108">Type of variant:</span></span>
    
    - <span data-ttu-id="1f85f-109">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1f85f-109">PT_LONG</span></span>
    
    - <span data-ttu-id="1f85f-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1f85f-110">PT_UNICODE</span></span>
    
    - <span data-ttu-id="1f85f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1f85f-111">PT_BINARY</span></span>
    
<span data-ttu-id="1f85f-112">_dw_</span><span class="sxs-lookup"><span data-stu-id="1f85f-112">_dw_</span></span>
  
> <span data-ttu-id="1f85f-113">变量型的 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="1f85f-113">DWORD value of variant.</span></span>
    
<span data-ttu-id="1f85f-114">_pwsz_</span><span class="sxs-lookup"><span data-stu-id="1f85f-114">_pwsz_</span></span>
  
> <span data-ttu-id="1f85f-115">variant 的字符串值。</span><span class="sxs-lookup"><span data-stu-id="1f85f-115">String value of variant.</span></span>
    
<span data-ttu-id="1f85f-116">_bin_</span><span class="sxs-lookup"><span data-stu-id="1f85f-116">_bin_</span></span>
  
> <span data-ttu-id="1f85f-117">变量的二进制值。</span><span class="sxs-lookup"><span data-stu-id="1f85f-117">Binary value of the variant.</span></span>
    

