---
title: HexFromBin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HexFromBin
api_type:
- COM
ms.assetid: 12b95657-1926-4a24-be63-40305ea6f990
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f68de5e18d84c728241c188b932f99456f5be8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584833"
---
# <a name="hexfrombin"></a><span data-ttu-id="a4f6b-103">HexFromBin</span><span class="sxs-lookup"><span data-stu-id="a4f6b-103">HexFromBin</span></span>

  
  
<span data-ttu-id="a4f6b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4f6b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4f6b-105">将二进制数转换为十六进制数的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-105">Converts a binary number into a string representation of a hexadecimal number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4f6b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a4f6b-106">Header file:</span></span>  <br/> |<span data-ttu-id="a4f6b-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a4f6b-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a4f6b-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="a4f6b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a4f6b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a4f6b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a4f6b-110">调用：</span><span class="sxs-lookup"><span data-stu-id="a4f6b-110">Called by:</span></span>  <br/> |<span data-ttu-id="a4f6b-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a4f6b-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void HexFromBin(
  LPBYTE pb,
  int cb,
  LPSTR sz
);
```

## <a name="parameters"></a><span data-ttu-id="a4f6b-112">参数</span><span class="sxs-lookup"><span data-stu-id="a4f6b-112">Parameters</span></span>

 <span data-ttu-id="a4f6b-113">_pb_</span><span class="sxs-lookup"><span data-stu-id="a4f6b-113">_pb_</span></span>
  
> <span data-ttu-id="a4f6b-114">[in]指向要转换的二进制数据的指针。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-114">[in] Pointer to the binary data to be converted.</span></span> 
    
 <span data-ttu-id="a4f6b-115">_cb_</span><span class="sxs-lookup"><span data-stu-id="a4f6b-115">_cb_</span></span>
  
> <span data-ttu-id="a4f6b-116">[in]大小 （以字节为单位， _pb_参数指向的二进制数据）。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-116">[in] Size, in bytes, of the binary data pointed to by the  _pb_ parameter.</span></span> 
    
 <span data-ttu-id="a4f6b-117">_sz_</span><span class="sxs-lookup"><span data-stu-id="a4f6b-117">_sz_</span></span>
  
> <span data-ttu-id="a4f6b-118">[输出]以 null 结尾的 ASCII 字符串表示的十六进制数字中的二进制数据的指针。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-118">[out] Pointer to a null-terminated ASCII string representing the binary data in hexadecimal digits.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a4f6b-119">返回值</span><span class="sxs-lookup"><span data-stu-id="a4f6b-119">Return value</span></span>

<span data-ttu-id="a4f6b-120">无。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a4f6b-121">注解</span><span class="sxs-lookup"><span data-stu-id="a4f6b-121">Remarks</span></span>

<span data-ttu-id="a4f6b-122">**HexFromBin**函数对其大小由_cb_参数的二进制数据的单位采用一个指针。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-122">The **HexFromBin** function takes a pointer to a unit of binary data whose size is indicated by the  _cb_ parameter.</span></span> <span data-ttu-id="a4f6b-123">它在返回_sz_字符串中 (2 \* _cb_) + 1 字节的内存，用十六进制数字此二进制信息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-123">It returns in the  _sz_ string, within (2\*  _cb_)+1 bytes of memory, a representation of this binary information in hexadecimal numbers.</span></span> <span data-ttu-id="a4f6b-124">如果字节值为小数 10，例如的十六进制字符串将 0A，这样一个字节转换为字符串中的两个字节。</span><span class="sxs-lookup"><span data-stu-id="a4f6b-124">If the byte value is decimal 10, for example, the hexadecimal string will be 0A, so one byte converts to two bytes in the string.</span></span> 
  

