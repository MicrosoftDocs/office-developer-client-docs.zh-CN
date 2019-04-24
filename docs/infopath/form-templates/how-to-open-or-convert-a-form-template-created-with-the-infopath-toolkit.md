---
title: 打开或转换用 InfoPath 工具包创建的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- converting form templates [infopath 2007],InfoPath Toolkit, opening form templates from,form templates [InfoPath 2007], opening,InfoPath 2007, converting InfoPath Toolkit form templates,opening form templates [InfoPath 2007],form templates [InfoPath 2007], converting,script [InfoPath 2007], converting to managed code
localization_priority: Normal
ms.assetid: af8eca2e-ba9a-4c37-94af-662815fff518
description: 如果您使用某个 InfoPath 2003 Toolkits for Visual Studio 创建了 InfoPath 2003 托管代码表单模板，并且希望保持与 InfoPath 2003 的兼容性，只需在 Microsoft InfoPath 和 Visual Studio 2008 中打开您的表单模板项目，即可继续处理和进一步开发该项目。
ms.openlocfilehash: 0acbfab4a83a71d94a1c70a667a963056f5b9a38
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300110"
---
# <a name="open-or-convert-a-form-template-created-with-the-infopath-toolkit"></a>打开或转换用 InfoPath 工具包创建的表单模板

如果您使用某个 InfoPath 2003 Toolkits for Visual Studio 创建了 InfoPath 2003 托管代码表单模板，并且希望保持与 InfoPath 2003 的兼容性，只需在 Microsoft InfoPath 和 Visual Studio 2008 中打开您的表单模板项目，即可继续处理和进一步开发该项目。
  
您也可以迁移和升级 InfoPath 2003 项目中的代码，以使用由 [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的新的 .NET 项目模型。执行该操作时，将需要重新编写所有代码，以使用 **Microsoft.Office.InfoPath** 命名空间的成员，但以前项目的所有代码都将保留，并用 **#if InfoPathManagedObjectModel** 和 **#endif** (C#) 或者 **#If InfoPathManagedObject Model** 和 **#End If** (Visual Basic) 语句围起来，以供您参考。 
  
下面的过程描述了如何打开使用 InfoPath 工具包创建的托管代码表单模板，并保持与 InfoPath 2003 的兼容性，或迁移和升级到新的 InfoPath 对象模型。 
  
### <a name="open-a-managed-code-form-template-created-with-the-infopath-toolkit-and-maintain-compatibility-with-infopath-2003-using-visual-studio-tools-for-applications"></a>打开使用 InfoPath 工具包创建的托管代码表单模板，并保持与使用 Visual Studio Tools for Applications 的 InfoPath 2003 的兼容性

1. 打开 InfoPath Designer，然后单击“文件”**** 选项卡上的“打开”****。 
    
2. 在“在设计模式中打开”**** 对话框中，导航到保存 InfoPath 工具包表单模板项目的项目文件夹。 
    
    默认情况下，这是创建项目的计算机上的  `C:\Users\` *用户名*  `\Documents\Visual Studio Projects` 中的文件夹。您也可以将该文件夹移动到 InfoPath 存储 Visual Studio 2008 项目的位置，该位置默认情况下为  `C:\Users\` *用户名*  `\Documents\InfoPath Projects`
    
3. 单击名为 manifest.xsf 的文件，然后单击“打开”****。
    
4. 在“开发工具”**** 选项卡上，单击“代码编辑器”****。
    
5. The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue. 
    
6. 导航到要保存文件的位置，命名该文件，然后单击 **"保存"**。
    
7. The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue. 
    
8. 选择项目的 Visual Studio 解决方案 (.sln) 文件，然后单击“打开”****。
    
9. The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue. 
    
10. 将显示消息"此表单中的代码使用 InfoPath 2003 对象模型"，并显示提示"是否升级代码，以使用 Microsoft Office InfoPath 对象模型?"。单击 **"否"** 将保持与 InfoPath 2003 的兼容性，并继续使用由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间提供的对象模型。 
    
    有关如何使用与 InfoPath 2003 兼容的托管代码表单模板的信息，请参阅[使用 InfoPath 2003 对象模型开发表单模板](developing-form-templates-using-the-infopath-2003-object-model.md)。
    
### <a name="open-a-managed-code-form-template-created-with-the-infopath-toolkit-and-upgrade-it-to-use-the-new-infopath-object-model-using-visual-studio-tools-for-applications"></a>打开使用 InfoPath 工具包创建的托管代码表单模板，并使用 Visual Studio Tools for Applications 升级该模板以使用新的 InfoPath 对象模型

1. 打开 InfoPath Designer，然后单击“文件”**** 选项卡上的“打开”****。 
    
2. 在 **"打开表单模板"** 下，单击 **"在'我的电脑'上"**。
    
3. 在“在设计模式中打开”**** 对话框中，导航到保存 InfoPath 工具包表单模板项目的项目文件夹。 
    
    默认情况下，这是创建项目的计算机上的  `C:\Users\` *用户名*  `\Documents\Visual Studio Projects` 中的文件夹。您也可以将该文件夹移动到 InfoPath 存储 Visual Studio 2008 项目的位置，该位置默认情况下为  `C:\Users\` *用户名*  `\Documents\InfoPath Projects`
    
4. 单击名为 manifest.xsf 的文件，然后单击“打开”****。
    
5. 在“开发工具”**** 选项卡上，单击“代码编辑器”****。
    
6. The message "This form template must be saved before you can add Visual Basic or C# code to it" is displayed. Click **OK** to continue. 
    
7. 导航到要保存文件的位置，命名该文件，然后单击 **"保存"**。
    
8. The message "This code was created with one of the InfoPath 2003 Toolkits for Microsoft Visual Studio. InfoPath needs to migrate the toolkit project to a new format" is displayed. Click **OK** to continue. 
    
9. 选择项目的 Visual Studio 解决方案 (.sln) 文件，然后单击“打开”****。
    
10. The message "Your project has been migrated" is displayed when the migration process is complete. Click **OK** to continue. 
    
11. The message "The code in this form uses the InfoPath 2003 object model" is displayed with the prompt "Do you want to upgrade your code to use the Microsoft Office InfoPath object model?" Click **Yes** to upgrade the form template to use the new managed code object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace. 
    
    将在 Visual Studio 2008 代码编辑器中打开您的表单代码，并且以前项目中的所有代码都用 **#if** **InfoPathManagedObjectModel** 和 **#endif** (C#) 或者 **#If InfoPathManagedObjectModel** 和 **#End If** (Visual Basic) 语句围起来，以供您参考。将需要重新编写所有这些代码，以使用由 **Microsoft.Office.InfoPath** 命名空间提供的对象模型的成员。 
    
    有关如何处理使用新的 InfoPath 托管代码对象模型的托管代码表单模板的信息，请参阅[开发包含代码的 InfoPath 表单模板](developing-infopath-form-templates-with-code.md)。
    

