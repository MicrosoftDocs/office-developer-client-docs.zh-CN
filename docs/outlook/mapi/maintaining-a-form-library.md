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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298458"
---
# <a name="maintaining-a-form-library"></a>维护表单库

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单库包含有关表单的所有重要信息: 其属性、谓词和其服务器的可执行文件。 某些客户端允许其用户维护、安装或删除表单服务器。 如果要向您的用户提供此功能, 您必须具有以下权限:
  
- 表单服务器的配置文件, 带有的文件。CFG 扩展。
    
- 表单库的容器对象, 是一个实现[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口的对象。 
    
若要访问配置文件或其路径名, 请使用任何方法都方便。 通常情况下, 客户端会向用户显示一个对话框, 用于安装和删除窗体服务器, 该对话框还可用于提示用户输入配置文件的位置。
  
若要访问表单库的容器, 请调用表单管理器的[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)方法。 传入枚举值以指定要打开的表单库, 如有必要, 将指向表单管理器打开表单库时应使用的对象的指针。 例如, 如果要打开[文件夹表单库](folder-form-libraries.md), 请传递[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)指针。 
  
在**OpenFormContainer**返回**IMAPIFormContainer**指针后, 调用[IMAPIFormContainer:: InstallForm](imapiformcontainer-installform.md)或[IMAPIFormContainer:: RemoveForm](imapiformcontainer-removeform.md), 具体取决于要执行的维护。 **InstallForm**将窗体服务器添加到库中;**RemoveForm**从库中删除表单服务器。 
  

