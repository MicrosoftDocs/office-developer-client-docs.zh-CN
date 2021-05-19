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
description: 从数字中返回 Unicode 字符。
ms.openlocfilehash: 81e76b72da35f79dee9ad6afbde51bc2e228483c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417579"
---
# <a name="unichar-function"></a>UNICHAR 函数

从数字中返回 Unicode 字符。 
  
## <a name="syntax"></a>语法

UNICHAR (** *number* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Integer** <br/> |1 到 65,535 之间（包括 1 和 65,535）的整数，若超出此范围，该函数将返回错误。  <br/> |
   
## <a name="remarks"></a>备注

生成的字符串的长度为一个 Unicode 字符（两个字符）。 
  
## <a name="example"></a>示例

UNICHAR (65)  
  
返回一 (拉丁文大写字母 A)  
  

