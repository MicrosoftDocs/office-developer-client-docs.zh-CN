---
title: 使用 Unicode 列
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2cd55464-263f-4f83-b874-524271773934
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 76d1afb750dc81b889ca8e5eb3639145c061bfc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408381"
---
# <a name="working-with-unicode-columns"></a>使用 Unicode 列

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以使用标准 8 位字符（属性类型 PT_STRING8）或 16 位 Unicode 字符（属性类型为 PT_UNICODE）来表示表中的字符串。 表实施者可以选择其表是否支持 Unicode 字符串。 由于 Unicode 通过扩展功能集为客户端和服务提供商增加了价值，因此建议尽可能支持 Unicode。 
  
许多表方法接受一个标志，指示字符串属性值预期是否是 Unicode。 在输入时，指定 MAPI_UNICODE 标志将指示表实现程序，调用传入的所有字符串属性值都是 Unicode 字符串，并且其属性类型为 PT_UNICODE。 在输出时，此标志指示所有返回的字符串属性值应为 Unicode 字符串（如果可能）。 标志是否具有输入或输出的含义取决于 方法。 不支持 Unicode 且传递给 MAPI_UNICODE 的表实现器将返回MAPI_E_BAD_CHAR_WIDTH值。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

