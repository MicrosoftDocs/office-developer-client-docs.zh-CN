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
  
MFCMAPI 示例使用消息传递 API 通过图形用户界面提供对 MAPI 存储的访问权限。 下载此示例后，可以使用源文件检查许多 MAPI 接口和引用的示例用例。 有关详细信息，请参阅 [MAPI Interfaces](mapi-interfaces.md)。
  
|||
|:-----|:-----|
|平台：  <br/> |Microsoft Visual Studio 2008 针对 Windows 7、Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 进行编译  <br/> |
   
### <a name="to-download-mfcmapi"></a>下载 MFCMAPI
  
1. 在 ["MFCMAPI"](https://codeplex.com/MFCMAPI) 页上，单击" **源代码"** 选项卡。 
    
2. 在 **"最近签入"下**，单击 **"下载** 最新内部版本"。 
    
3. 阅读许可协议，然后单击"**我同意"。**
    
4. 在“文件下载”对话框中，单击“保存”。 在 **"另存为**"对话框中，找到要保存源文件的文件夹，然后单击"保存 **"。**
    
5. 在"**下载完成"** 对话框中，单击"**打开文件夹"。** 还可以单击 **"关闭** "关闭对话框，并找到保存这些文件的文件夹中的压缩源文件。 
    
6. 右键单击 **MFCMAPI- \<.zip\>** 文件，然后单击"全部 **提取"。** 在出现的对话框中，单击" **提取** "以将文件解压缩到显示的文件夹。 也可以单击"浏览 **"** 选择或创建其他文件夹。 
    
7. 以Visual Studio运行 2008 年 6 月。
    
   > [!NOTE]
   > 如果计算机在 XP Windows，则必须以管理员身份登录。 如果计算机在 Vista Windows，则必须以管理员身份登录，并且必须右键单击 Visual Studio 2008 图标，然后单击"以管理员身份 **运行"。** 
  
8. 在 Visual Studio 2008 中，单击"文件"，指向"打开"，然后单击 **"Project/解决方案"。**
    
9. 浏览到保存示例的位置，选择 **"MFCMapi.vcproj"，** 然后单击"打开 **"。**
    
10. 在"构建"菜单上，单击"构建解决方案"。
    
11. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a>使用 MFCMAPI 作为代码示例
  
在 **"解决方案资源管理器**"中，展开 **MFCMapi** 项目并检查"头文件"、"**资源** 文件"和"源文件"节点中的文件，以用于编程方案。  
  
MAPI 接口部分 [中的许多](mapi-interfaces.md) 方法主题指向 MFCMAPI 源文件，用于编程示例。 例如，在 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 中，会指示您查看  `CMsgStoreDlg::OnDisplayReceiveFolderTable` MsgStoreDlg.cpp 文件中的函数。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 示例](mapi-samples.md)

