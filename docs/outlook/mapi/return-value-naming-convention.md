---
title: 返回值命名约定
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c1cdd7b-82f1-46f2-a7ce-e0efe857b7cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6786e1ca901215abd709a11401c3026d62c6ffc8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423613"
---
# <a name="return-value-naming-convention"></a>返回值命名约定

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPICODE。H 头文件包含客户端或服务提供商可能从接口方法实现返回或可能从调用返回的许多值。
  
表示警告和失败条件的代码遵循不同的命名约定，该约定以前缀 MAPI、下划线和 W 或 E 开头，以指示代码类型。 代码的其余部分是一个短字符串，用于描述条件。 字符串中的每个单词都用下划线分隔。 例如，错误值 MAPI_E_TOO_COMPLEX指示实现无法处理调用中请求的任何操作。 警告值MAPI_W_PARTIAL_COMPLETION指示调用成功，但出现问题。 只有部分操作成功完成。
  

