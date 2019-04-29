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
  
Windows SDK 附带的默认 MAPI 表单管理器不提供用于在各种表单库中安装表单的用户界面。 因此, 您必须创建一个小型应用程序 (或详细的说明集), 以便用户可以使用它来安装表单。
  
如果实现安装应用程序, 则必须执行的一系列操作将表单安装到文件夹的关联内容表中, 如下所示:
  
1. 调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数以打开窗体管理器。 
    
2. 使用[IMAPIFormMgr:: OpenFormContainer](imapiformmgr-openformcontainer.md)或[IMAPIFormMgr:: SelectFormContainer](imapiformmgr-selectformcontainer.md)方法可选择和打开表单的目标容器。 
    
3. 使用[IMAPIFormContainer:: InstallForm](imapiformcontainer-installform.md)函数安装表单。 
    
    步骤4至6用于安装到本地表单库:
    
4. 将所有文件复制到本地磁盘上的适当位置 (如果安装指向用户工作站上的本地表单库)。 如有必要, 请修改表单配置文件以反映组件的当前路径。 表单配置文件可以包含相对路径, 在这种情况下, 此步骤可能不是必需的。
    
5. 完成相应的 OLE 注册步骤, 将邮件类型与要安装的窗体服务器相关联。
    
6. 如果表单已安装到本地表单库中, 则将表单的图标 (.ico) 和配置 (cfg) 文件复制到%WINDOWS%\FORMS\CONFIGS 目录中, 以便在表单库损坏或删除时可以自动还原表单。 建议使用此步骤, 但不是强制性步骤。
    
> [!NOTE]
> 您可以通过将步骤1和2替换为对[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数的调用来简化到本地表单库的安装。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

