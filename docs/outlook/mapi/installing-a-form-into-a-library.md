---
title: 将表单安装到库中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 303c9dcb-f9b5-4cea-b5f2-3eba01aa3b09
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d3b20c9fb4b4f1a26eb4ed1a9a498bd56a915a70
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579779"
---
# <a name="installing-a-form-into-a-library"></a>将表单安装到库中

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
与 Windows SDK 一起提供的默认 MAPI 窗体管理器不提供安装在不同的表单库中的窗体的用户界面。 因此，您将需要创建一个小应用程序 — 或详细说明 — 用户可用来安装该表单。
  
如果实现安装应用程序，操作的一系列它必须执行安装窗体到表如下所示的某个文件夹的相关内容：
  
1. 调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开窗体管理器。 
    
2. [IMAPIFormMgr::OpenFormContainer](imapiformmgr-openformcontainer.md)或[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)方法用于选择并打开窗体的目标容器。 
    
3. 使用[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)函数安装该表单。 
    
    步骤 4 至 6 供安装到本地表单库：
    
4. 如果安装到用户的工作站上的本地窗体库，将所有文件都复制到本地磁盘上的适当位置。 如有必要，修改窗体配置文件，以反映当前路径的组件。 窗体配置文件可以包含的相对路径，在这种情况下此步骤可能不要求。
    
5. 完成相应的 OLE 注册步骤将邮件类型与所安装的窗体服务器相关联。
    
6. 如果窗体已安装到本地窗体库中，复制该窗体的图标 (.ico) 和配置 (.cfg) 文件到 %WINDOWS%\FORMS\CONFIGS 目录，以便表单可以自动还原表单库已损坏或已删除的情况下。 建议，但不是强制性，此步骤。
    
> [!NOTE]
> 通过调用[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数替换为步骤 1 和 2 可以简化安装到本地表单库。 
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

