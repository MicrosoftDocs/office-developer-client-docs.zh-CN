---
title: 命名约定的返回值
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c1cdd7b-82f1-46f2-a7ce-e0efe857b7cd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 990a48c661621a3a704236a850f5d09239a12fca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778652"
---
# <a name="return-value-naming-convention"></a>命名约定的返回值

  
  
**适用于**： Outlook 
  
MAPICODE。H 头文件中包含许多客户端或服务提供程序可能会返回从接口方法实现或可能会看到呼叫从返回的值。
  
表示警告和失败情况的代码按照不同的命名约定的开头的前缀 MAPI、 下划线和 W 或 E，指示的代码的类型。 代码的其余是一个简短的字符串，以描述此条件。 由下划线分隔字符串中的每个单词。 例如，错误值 MAPI_E_TOO_COMPLEX 指示实现无法处理呼叫中要请求的内容。 警告值 MAPI_W_PARTIAL_COMPLETION 指示的调用成功，但时出现问题。 成功完成仅操作的一部分。
  

