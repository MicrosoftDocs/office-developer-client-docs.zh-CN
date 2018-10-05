---
title: MFCMAPI 作为的代码示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f98eb842-fe76-4f60-b5e2-d2217d1a66ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d72c224db8b3ae4bb6fee3d34f73d9949cda6b8d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391657"
---
# <a name="mfcmapi-as-a-code-sample"></a>MFCMAPI 作为的代码示例
 
**适用于**：Outlook 2013 | Outlook 2016 
  
MFCMAPI 示例使用消息 API 来提供对通过图形用户界面的 MAPI 存储的访问。 下载此示例之后，您可以使用的源文件要检查的许多 MAPI 接口和引用的示例使用情况。 有关详细信息，请参阅[MAPI 接口](mapi-interfaces.md)。
  
|||
|:-----|:-----|
|平台：  <br/> |Microsoft Visual Studio 2008 编译为 Windows 7、 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1  <br/> |
   
### <a name="to-download-mfcmapi"></a>若要下载 MFCMAPI
  
1. 在[MFCMAPI](https://codeplex.com/MFCMAPI)页上，单击**源代码**选项卡。 
    
2. 在**最近的签入**下的最新的生成单击**下载**。 
    
3. 阅读许可协议，，，然后单击**我同意**。
    
4. 在**文件下载**对话框中，单击**保存**。 在**另存为**对话框中，找到您要在其中保存源文件的文件夹，然后单击**保存**。
    
5. 在**下载完毕**对话框中，单击**打开文件夹**。 您还可以单击**关闭**以关闭对话框并保存其文件夹中找到的压缩的源文件。 
    
6. 右键单击**MFCMAPI-\<版本号\>.zip**文件，，然后单击**全部提取**。 在出现的对话框中，单击**提取**以将文件提取到的文件夹的显示。 您还可以单击**浏览**以选择或创建不同的文件夹。 
    
7. 以管理员身份运行 Visual Studio 2008。
    
   > [!NOTE]
   > 如果您的计算机运行 Windows XP，您必须以管理员身份登录。 如果您的计算机运行 Windows Vista，您必须以管理员身份登录，您必须右键单击 Visual Studio 2008 图标，然后单击**以管理员身份运行**。 
  
8. 在 Visual Studio 2008 中，单击**文件**，指向**打开**，，然后单击**项目/解决方案**。
    
9. 浏览到保存该示例的位置，选择**MFCMapi.vcproj**，，然后单击**打开**。
    
10. 在"构建"菜单上，单击"构建解决方案"。
    
11. 在**将文件另存为**对话框中，单击**保存**。
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a>使用 MFCMAPI 作为的代码示例
  
在**解决方案资源管理器**中，展开**MFCMapi**项目，并检查编程方案**头文件**、**资源文件**和**源文件**节点中的文件。 
  
在[MAPI 接口](mapi-interfaces.md)部分中的许多方法主题指向 MFCMAPI 源文件的编程示例。 例如，在[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)指示可以这样看待函数`CMsgStoreDlg::OnDisplayReceiveFolderTable`MsgStoreDlg.cpp 文件中。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 示例（英文）](mapi-samples.md)

