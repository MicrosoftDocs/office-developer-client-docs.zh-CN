---
title: UNICHAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60117
localization_priority: Normal
ms.assetid: 371a475d-50f7-6b4c-4b47-581cd778dcba
description: 返回数字的 Unicode 字符。
ms.openlocfilehash: 06f97717ee4d5965253b0da7cfd5c35faf0ca2f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781596"
---
# <a name="unichar-function"></a>UNICHAR 函数

返回数字的 Unicode 字符。 
  
## <a name="syntax"></a>语法

UNICHAR (* **数量** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Integer** <br/> |1 到 65,535 之间（包括 1 和 65,535）的整数，若超出此范围，该函数将返回错误。  <br/> |
   
## <a name="remarks"></a>注解

生成的字符串的长度为一个 Unicode 字符（两个字符）。 
  
## <a name="example"></a>示例

UNICHAR(65) 
  
返回 A （拉丁文大写字母 A） 
  

