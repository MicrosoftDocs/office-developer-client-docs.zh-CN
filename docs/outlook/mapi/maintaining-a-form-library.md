---
title: 维护表单库
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8488f7ec-e44b-4d1a-ba42-baea8c71d350
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5ccb5a2881d3cef3ff21a106e7e9ea33e0aedd9e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776161"
---
# <a name="maintaining-a-form-library"></a>维护表单库

  
  
**适用于**： Outlook 
  
表单库保留所有窗体的重要信息： 其属性、 其谓词和所在服务器的可执行文件。 某些客户端允许其用户进行维护、 安装或删除表单服务器。 如果您想要向用户提供此功能，您必须有权：
  
- 窗体服务器的配置文件、 的文件。配置扩展。
    
- 表单库的容器对象，实现的对象[IMAPIFormContainer: IUnknown](imapiformcontaineriunknown.md)接口。 
    
若要访问的配置文件或向其使用路径名任何方法是方便。 通常情况下，客户端向用户显示一个对话框，安装和删除还可用于提示用户输入配置文件的位置的窗体服务器。
  
若要访问表单库的容器，调用窗体经理[IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)方法。 传入的枚举值，以指定的表单库，若要打开，如有必要，指向窗体管理器应使用打开的表单库的对象的指针。 例如，如果您打开[文件夹表单库](folder-form-libraries.md)，传递[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)指针。 
  
**OpenFormContainer**返回**IMAPIFormContainer**指针后，调用[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)或[IMAPIFormContainer::RemoveForm](imapiformcontainer-removeform.md)，具体取决于要执行的维护。 **InstallForm**将窗体服务器添加到库中;**RemoveForm**从库中删除的窗体服务器。 
  

