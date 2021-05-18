---
title: 维护表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8488f7ec-e44b-4d1a-ba42-baea8c71d350
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 51c7c3f8ba70dcb3d35dc50806e984fd4b193818
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408801"
---
# <a name="maintaining-a-form-library"></a>维护表单库

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单库包含有关表单的所有重要信息：其属性、其谓词及其服务器的可执行文件。 某些客户端允许用户维护、安装或删除表单服务器。 如果要向用户提供此功能，则必须有权访问：
  
- 表单服务器的配置文件，一个包含 的文件。CFG 扩展。
    
- 表单库的容器对象，一个实现 [IMAPIFormContainer ： IUnknown 接口](imapiformcontaineriunknown.md) 的对象。 
    
若要访问配置文件或路径名，请使用任何方便的方式。 通常，客户端会向用户显示一个对话框，用于安装和删除表单服务器，该对话框还可用于提示用户输入配置文件的位置。
  
若要访问表单库的容器，请调用表单管理器的 [IMAPIFormMgr：：OpenFormContainer](imapiformmgr-openformcontainer.md) 方法。 传递枚举值以指定要打开的表单库，以及指向表单管理器用于打开表单库的对象的指针（如有必要）。 例如，如果要打开文件夹表单 [库](folder-form-libraries.md)，请传递 [IMAPIFolder ：IMAPIContainer](imapifolderimapicontainer.md) 指针。 
  
**OpenFormContainer** 返回 **IMAPIFormContainer** 指针后，根据要执行的维护调用 [IMAPIFormContainer：：InstallForm](imapiformcontainer-installform.md)或 [IMAPIFormContainer：：RemoveForm。](imapiformcontainer-removeform.md) **InstallForm** 将表单服务器添加到库中; **RemoveForm** 从库中删除表单服务器。 
  

