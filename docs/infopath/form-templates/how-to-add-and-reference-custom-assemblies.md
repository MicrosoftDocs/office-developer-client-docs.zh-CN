---
title: 添加和引用自定义程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, using custom assemblies,assemblies [InfoPath 2007], adding custom using InfoPath 2003 object model
localization_priority: Normal
ms.assetid: 20e1f43e-8279-48fc-8f34-16a2729dbc9b
description: 如果在托管代码表单模板项目中添加一个对自定义程序集的引用，则编译和发布项目时，该程序集将包含在表单模板文件 (.xsn) 内。
ms.openlocfilehash: 19b5f06231bb03cfac8b32b157e03956b5fc334e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431167"
---
# <a name="add-and-reference-custom-assemblies"></a>添加和引用自定义程序集

如果在托管代码表单模板项目中添加一个对自定义程序集的引用，则编译和发布项目时，该程序集将包含在表单模板文件 (.xsn) 内。
  
## <a name="add-and-reference-a-custom-assembly"></a>添加和引用自定义程序集

为了避免与 InfoPath 项目系统管理文件（即添加到表单模板中文件）的方式相冲突，请勿将要引用的任何自定义程序集复制到表单模板项目的顶级文件夹中。默认情况下，其路径的格式如下：< *驱动器*  >:\Users\  *用户名*  \Documents\InfoPath Projects\  *项目名* 
  
如果确实要将所引用的自定义程序集移动到项目文件夹内的某个位置，则必须在主项目文件夹下创建一个子文件夹，然后从该子文件夹复制和引用自定义程序集。但是请注意，为引用的程序集创建子文件夹不是必需的。只要引用的程序集不在项目的顶级文件夹内，InfoPath 项目系统就会在编译和发布项目时，将程序集复制到表单模板文件 (.xsn) 中。
  
### <a name="reference-a-custom-assembly-from-its-default-location"></a>从默认位置引用自定义程序集

1. 在 Visual Studio 2008 中打开表单模板项目。
    
2. 在“项目”菜单上，单击“添加引用”。
    
3. 单击“浏览”选项卡，找到并指定程序集，再单击“确定”，以添加引用。 
    
## <a name="see-also"></a>另请参阅

#### <a name="tasks"></a>任务

[使用 InfoPath 2003 对象模型创建表单模板](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)

