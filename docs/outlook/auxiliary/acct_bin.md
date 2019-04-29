---
title: ACCT_BIN
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5b57296c-61d7-e517-7ab7-44a9cc1f7ffc
description: 此数据类型的变量包含二进制值。
ms.openlocfilehash: 3dcaaf73a04ddc608e68ca7bd1f801d0a5d99bb6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408122"
---
# <a name="acctbin"></a><span data-ttu-id="665ee-103">ACCT_BIN</span><span class="sxs-lookup"><span data-stu-id="665ee-103">ACCT_BIN</span></span>

<span data-ttu-id="665ee-104">此数据类型的变量包含二进制值。</span><span class="sxs-lookup"><span data-stu-id="665ee-104">A variable of this data type holds a binary value.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="665ee-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="665ee-105">Quick info</span></span>

```cpp
typedef struct { 
    DWORDcb; 
    BYTE * pb; 
} ACCT_BIN; 

```

## <a name="members"></a><span data-ttu-id="665ee-106">成员</span><span class="sxs-lookup"><span data-stu-id="665ee-106">Members</span></span>

<span data-ttu-id="665ee-107">_cb_</span><span class="sxs-lookup"><span data-stu-id="665ee-107">_cb_</span></span>
  
> <span data-ttu-id="665ee-108">_pb_指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="665ee-108">Number of bytes that  _pb_ points to.</span></span> 
    
<span data-ttu-id="665ee-109">_pb_</span><span class="sxs-lookup"><span data-stu-id="665ee-109">_pb_</span></span>
  
> <span data-ttu-id="665ee-110">指向二进制信息的指针。</span><span class="sxs-lookup"><span data-stu-id="665ee-110">Pointer to binary information.</span></span>
    

