---
title: 将表单安装到库中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 303c9dcb-f9b5-4cea-b5f2-3eba01aa3b09
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 08470a80153e42136922ae502252d83de0125512
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433141"
---
# <a name="installing-a-form-into-a-library"></a>将表单安装到库中

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
随 Windows SDK 提供的默认 MAPI 表单管理器不提供用于在各种表单库中安装表单的用户界面。 因此，您必须创建一个小型应用程序或一组详细的说明，以便用户安装表单。
  
如果实现安装应用程序，则必须执行一系列操作才能将表单安装到文件夹的关联内容表中，如下所示：
  
1. 调用 [MAPIOpenFormMgr](mapiopenformmgr.md) 函数以打开表单管理器。 
    
2. 使用 [IMAPIFormMgr：：OpenFormContainer](imapiformmgr-openformcontainer.md) 或 [IMAPIFormMgr：：SelectFormContainer](imapiformmgr-selectformcontainer.md) 方法选择并打开表单的目标容器。 
    
3. 使用 [IMAPIFormContainer：：InstallForm](imapiformcontainer-installform.md) 函数安装表单。 
    
    步骤 4 至步骤 6 适用于安装在本地表单库中：
    
4. 如果安装在用户工作站上的本地表单库中，则复制所有文件到本地磁盘上的适当位置。 如有必要，修改表单配置文件以反映组件的当前路径。 表单配置文件可以包含相对路径，在这种情况下，可能不需要执行此步骤。
    
5. 完成相应的 OLE 注册步骤，将邮件类型与正在安装的表单服务器关联。
    
6. 如果表单已安装到本地表单库中，将表单的图标 (.ico) 和配置 (.cfg) 文件复制到 %WINDOWS%\FORMS\CONFIGS 目录中，以便表单在表单库损坏或删除时可以自动还原。 建议执行此步骤，但不强制执行此步骤。
    
> [!NOTE]
> 可以通过调用 [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) 函数来替换步骤 1 和步骤 2，从而简化到本地表单库的安装。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

