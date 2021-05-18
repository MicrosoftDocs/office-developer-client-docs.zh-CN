---
title: DECIMALSEP 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251883
localization_priority: Normal
ms.assetid: 091fe401-05b2-464f-9333-7bb7118cd7cd
description: 返回当前用户区域设置的小数分隔符字符串。
ms.openlocfilehash: 8a59e7331fd51cf5426b5e2cdd64e3c5a22334b3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360303"
---
# <a name="decimalsep-function"></a><span data-ttu-id="9716f-103">DECIMALSEP 函数</span><span class="sxs-lookup"><span data-stu-id="9716f-103">DECIMALSEP Function</span></span>

<span data-ttu-id="9716f-104">返回当前用户区域设置的小数分隔符字符串。</span><span class="sxs-lookup"><span data-stu-id="9716f-104">Returns the decimal separator string for the current user locale.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9716f-105">语法</span><span class="sxs-lookup"><span data-stu-id="9716f-105">Syntax</span></span>

<span data-ttu-id="9716f-106">DECIMALSEP( )</span><span class="sxs-lookup"><span data-stu-id="9716f-106">DECIMALSEP( )</span></span>
  
## <a name="example"></a><span data-ttu-id="9716f-107">示例</span><span class="sxs-lookup"><span data-stu-id="9716f-107">Example</span></span>

<span data-ttu-id="9716f-108">SETF (GETREF (user.size) 、user.wholePart &amp; DECIMALSEP () &amp; user.fracPart) </span><span class="sxs-lookup"><span data-stu-id="9716f-108">SETF(GETREF(user.size), user.wholePart &amp; DECIMALSEP() &amp; user.fracPart)</span></span> 
  

