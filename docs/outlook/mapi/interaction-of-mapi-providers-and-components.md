---
title: MAPI 提供程序和组件的交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c0e010b-0432-4ef7-a243-3a4b46f0a19d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b88eafcc1ca6be98c5c1e9418072a5cb35f43345
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332170"
---
# <a name="interaction-of-mapi-providers-and-components"></a>MAPI 提供程序和组件的交互

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
任何种类的 MAPI 服务提供程序都必须遵循特定的准则来使用其他 MAPI 组件。 每个服务提供程序都必须:
  
- 使用正确的提供程序和登录对象进行初始化。
    
- 初始化时, 向邮件系统返回提供程序入口点的派送表。
    
- 为提供程序拥有的每个资源注册 MAPI 状态表行, 并在适当的时候调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法。 
    
- 使用[IMAPISupport:: NewUID](imapisupport-newuid.md)方法获取有效的唯一标识符 (uid)。 
    
- 支持它返回的对象上的常见 MAPI 接口。
    
- 使用 mapi 内存分配函数分配返回给客户端应用程序的内存, 并释放由 MAPI 子系统的其他部分分配的内存。
    
- 如果需要, 请维护配置文件部分, 以将凭据存储到基础邮件系统中。
    
- 使用[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法可注册任何邮件预处理函数。 
    
- 包括用于定义常见常量、结构、接口和返回值的适当头文件 (包括 mapispi)。
    
- 遵循常用地址类型的地址格式约定。
    

