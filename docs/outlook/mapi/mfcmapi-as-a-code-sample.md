---
title: 作为代码示例的 MFCMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f98eb842-fe76-4f60-b5e2-d2217d1a66ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d72c224db8b3ae4bb6fee3d34f73d9949cda6b8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356859"
---
# <a name="mfcmapi-as-a-code-sample"></a>作为代码示例的 MFCMAPI
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MFCMAPI 示例使用消息传递 API, 通过图形用户界面提供对 MAPI 存储的访问权限。 下载此示例后, 可以使用源文件检查许多 MAPI 接口和引用的示例使用情况。 有关详细信息, 请参阅[MAPI 接口](mapi-interfaces.md)。
  
|||
|:-----|:-----|
|平台  <br/> |Microsoft Visual Studio 2008 for windows 7、windows Vista、windows server 2008、windows XP SP2 和 windows Server 2003 SP1 的编译  <br/> |
   
### <a name="to-download-mfcmapi"></a>下载 MFCMAPI
  
1. 在 " [MFCMAPI](https://codeplex.com/MFCMAPI) " 页上, 单击 "**源代码**" 选项卡。 
    
2. 在 "**最近的签入**" 下, 单击 "**下载**" 以获取最新版本。 
    
3. 阅读许可协议, 然后单击 "**我同意**"。
    
4. 在“文件下载”**** 对话框中，单击“保存”****。 在 "**另存为**" 对话框中, 找到要在其中保存源文件的文件夹, 然后单击 "**保存**"。
    
5. 在 "**下载已完成**" 对话框中, 单击 "**打开文件夹**"。 您还可以单击 "**关闭**" 关闭对话框, 并在保存文件的文件夹中找到压缩的源文件。 
    
6. 右键单击**MFCMAPI\<号码\>.zip**文件, 然后单击 "**全部提取**"。 在出现的对话框中, 单击 "**提取**" 将文件提取到显示的文件夹中。 也可以单击 "**浏览**" 来选择或创建其他文件夹。 
    
7. 以管理员身份运行 Visual Studio 2008。
    
   > [!NOTE]
   > 如果您的计算机运行的是 Windows XP, 则必须以管理员身份登录。 如果你的计算机运行的是 Windows Vista, 则必须以管理员身份登录, 然后才能右键单击 Visual Studio 2008 图标, 然后单击 "以**管理员身份运行**"。 
  
8. 在 Visual Studio 2008 中, 单击 "**文件**", 指向 "**打开**", 然后单击 "**项目/解决方案**"。
    
9. 浏览到保存示例的位置, 选择 " **MFCMapi**", 然后单击 "**打开**"。
    
10. 在"构建"菜单上，单击"构建解决方案"。
    
11. 在 "**将文件另存为**" 对话框中, 单击 "**保存**"。
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a>将 MFCMAPI 用作代码示例
  
在 "**解决方案资源管理器**" 中, 展开 " **MFCMapi** " 项目, 然后检查**头文件**、**资源文件**和**源文件**节点中的文件, 以查看编程方案。 
  
[MAPI 接口](mapi-interfaces.md)部分中的许多方法主题指向用于编程示例的 MFCMAPI 源文件。 例如, 在[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)中, 系统会指示您查看 MsgStoreDlg 文件`CMsgStoreDlg::OnDisplayReceiveFolderTable`中的函数。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 示例（英文）](mapi-samples.md)

