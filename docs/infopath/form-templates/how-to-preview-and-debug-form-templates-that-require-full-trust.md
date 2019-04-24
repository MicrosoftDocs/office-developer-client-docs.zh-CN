---
title: 预览和调试需要完全信任的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- debugging [infopath 2007], infopath 2003-compatible form templates,previewing InfoPath 2003-compatible form templates,form templates [InfoPath 2007], previewing 2003-compatible,form templates [InfoPath 2007], debugging 2003-compatible,debugging InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: 5c491666-06f0-42ec-967e-1c70cd5e03a0
description: 默认情况下，如果您尝试调试或预览的托管代码项目所包含的代码调用需要完全信任的对象模型成员（例如 LoginName 属性，它需要访问有关用户登录域的信息），Microsoft InfoPath 将显示下列错误消息。
ms.openlocfilehash: 0780db286e2ca9cef381c2d24cb621c7c243dcb7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303596"
---
# <a name="preview-and-debug-form-templates-that-require-full-trust"></a>预览和调试需要完全信任的表单模板

默认情况下，如果您尝试调试或预览的托管代码项目所包含的代码调用需要完全信任的对象模型成员（例如 **LoginName** 属性，它需要访问有关用户登录域的信息），Microsoft InfoPath 将显示下列错误消息。 
  
预览时：
  
"表单代码中发生未处理的例外项"。接着将显示"由于该表单的代码中存在错误，InfoPath 无法完成此操作。"。
  
调试时：
  
焦点将移至代码编辑器中调用需要完全信任的成员的代码行，并将显示以下消息：" **SecurityException** 未由用户代码进行处理 - 请求失败"。 
  
要在调试或预览时允许表单模板的业务逻辑调用此成员，您必须按照下面的过程将表单模板的安全级别设为“完全信任”****。 
  
## <a name="configuring-a-managed-code-form-template-that-requires-full-trust"></a>配置需要完全信任的托管代码表单模板

### <a name="set-your-forms-security-level-to-full-trust"></a>将表单的安全级别设为"完全信任"

1. 在 InfoPath 中，在设计模式下打开表单模板。
    
2. 单击“文件”**** 选项卡，然后单击“信息”**** 选项卡上的“表单选项”****。 
    
3. 在“类别”**** 列表中，单击“安全和信任”****。
    
4. 在“安全级别”**** 下，清除“自动确定安全级别”****。
    
5. 选择“完全信任”****，然后单击“确定”****。
    
执行此过程后，您便可以按照[预览和调试包含代码的 InfoPath 表单模板](how-to-preview-and-debug-infopath-form-templates-with-code.md)中介绍的那样来调试项目了。
  
> [!NOTE]
> 要成功部署需要完全信任的托管代码表单模板，还需要执行其他一些步骤，例如进行数字签名或安装并注册表单模板。 有关在调试后部署托管代码表单模板的信息，请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。 
  
## <a name="see-also"></a>另请参阅



[预览和调试包含代码的 InfoPath 表单模板](how-to-preview-and-debug-infopath-form-templates-with-code.md)
  
[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)

