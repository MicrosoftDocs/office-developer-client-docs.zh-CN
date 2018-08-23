---
title: MAPI 提供程序与组件的交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c0e010b-0432-4ef7-a243-3a4b46f0a19d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c81da7673d6c0c59de6992bc46362069daf71b42
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592624"
---
# <a name="interaction-of-mapi-providers-and-components"></a>MAPI 提供程序与组件的交互

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
任何类型的 MAPI 服务提供程序必须遵循某些准则以使用 MAPI 的其他组件。 每个服务提供商必须：
  
- 用于初始化的适当的提供程序和登录对象。
    
- 消息系统初始化时返回调度表的提供程序入口点。
    
- 注册 MAPI 状态表格行的服务提供商拥有每个资源，并在适当的时间调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法。 
    
- 使用[IMAPISupport::NewUID](imapisupport-newuid.md)方法获取有效的唯一标识符 (Uid)。 
    
- 支持将返回的对象的常见的 MAPI 接口。
    
- 使用 MAPI 内存分配函数，以返回到客户端应用程序的内存分配并释放内存分配由 MAPI 子系统的其他部分。
    
- 维护配置文件节，，如有必要，存储到基础邮件系统的凭据。
    
- [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法用于注册任何消息预处理函数。 
    
- 包含适当的头文件 （包括 mapispi.h） 的定义常见常量、 结构、 接口和返回值。
    
- 按照地址格式约定常见的地址类型。
    

