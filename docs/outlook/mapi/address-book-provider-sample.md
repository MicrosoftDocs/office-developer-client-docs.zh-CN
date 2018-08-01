---
title: 通讯簿提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ccf1643-5604-4fee-92cc-3d6af00e7f98
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c32017598407760d5dbbb01ee6c28267bbffd152
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774508"
---
# <a name="address-book-provider-sample"></a>通讯簿提供程序示例

  
  
**适用于**： Outlook 
  
此示例显示名称和电子邮件地址，从平面二进制文件读取支持单个只读的容器。 此示例支持一次性模板和配置文件向导除外的所有配置选项。
  
您可以从[Outlook 消息处理 API (MAPI) 代码示例](http://go.microsoft.com/fwlink/?LinkId=129740
)下载此示例。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |SABP32.dll  <br/> |
| 源代码目录：  <br/> |SampleAddressBookProvider\SABP  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |Microsoft Visual Studio 2008 编译为 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能：
  
- 表限制。 本示例实现的前缀匹配和模糊名称解析。 它不实现完整的 MAPI 限制语言，并限制仅支持的显示名称。
    
- 消息的用户的详细信息显示表。 
    
- 一次性地址。
    
- 高级的搜索对话框。
    
- [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 部分支持此接口;其**IMAPIProp**方法将委派给**IPropData**接口。 有关详细信息，请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md)接口。 
    
- 交互式和编程方式配置。
    
## <a name="unsupported-features"></a>不支持的功能

此示例不支持以下功能：
  
- 排序。
    
- 通讯组列表。
    
- 创建、 删除和修改项。
    
- 具有多个值的属性。
    
- 命名的属性。
    
- 区分中的显示名称的第一个和最后一个名称。
    
 **安装示例通讯簿提供程序**
  
1. 若要下载示例通讯簿提供程序，请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到 Outlook MAPI 示例的保存位置的文件夹。 右键单击**OutlookMAPISamples-\<版本号\>** zip 文件夹，然后单击**全部提取**。
    
3. 单击**浏览**，选择要用于保存该示例的位置，然后单击**提取**。
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中，单击**文件**，选择**打开**，然后单击**项目/解决方案**。
    
6. 浏览到保存该示例的位置，单击**SABP.vcproj**，，然后单击**打开**。
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在**将文件另存为**对话框中，单击**保存**。
    
9. 在本示例保存的文件夹，右键单击**install.bat**文件，然后单击**以管理员身份运行**。
    
10. 在**用户帐户控制**对话框中，单击**继续**。
    
    > [!NOTE]
    > **Install.bat**复制.dll 默认 Microsoft Office 安装文件夹，C:\Program Files\Microsoft Office\Office12\. 如果您已在其他位置安装 Office 产品，右键单击**Install.bat** ，然后单击**编辑**。 在记事本中打开该文件。 默认安装路径替换为您的计算机上使用的安装路径。 
  

