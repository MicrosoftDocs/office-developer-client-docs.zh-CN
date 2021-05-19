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
ms.openlocfilehash: fa2a447d0757e75c95d7dc3d9b1dd16b8c7a8084
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331106"
---
# <a name="address-book-provider-sample"></a>通讯簿提供程序示例

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此示例支持显示名称和电子邮件地址（从平面二进制文件读取）的单个只读容器。 该示例支持一次使用模板以及除配置文件向导之外的所有配置选项。
  
可以从 MAPI 代码示例[Outlook消息 API (下载) 示例](https://go.microsoft.com/fwlink/?LinkId=129740
)。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |SABP32.dll  <br/> |
| 源代码目录：  <br/> |SampleAddressBookProvider\SABP  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |Microsoft Visual Studio 2008 针对 Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 进行编译  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能：
  
- 表限制。 此示例实现前缀匹配和模糊名称解析。 它不实现完整的 MAPI 限制语言，并且仅在该语言上支持显示名称。
    
- 邮件用户的详细信息显示表。 
    
- 一次使用的地址。
    
- 高级搜索对话框。
    
- [IMAPIStatus ：IMAPIProp](imapistatusimapiprop.md)接口。 此接口部分受支持;其 **IMAPIProp** 方法被委派给 **IPropData** 接口。 有关详细信息，请参阅 [IPropData ： IMAPIProp](ipropdataimapiprop.md) 接口。 
    
- 交互式和编程配置。
    
## <a name="unsupported-features"></a>不受支持的功能

此示例不支持以下功能：
  
- 排序。
    
- 通讯组列表。
    
- 创建、删除和修改条目。
    
- 具有多个值的属性。
    
- 命名属性。
    
- 区分显示名称中的名字和姓氏。
    
 **安装示例通讯簿提供程序**
  
1. 若要下载示例通讯簿提供程序，请参阅下载Outlook [MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 MAPI 示例Outlook的文件夹。 右键单击 **"OutlookMAPISamples- \< 版本号 \>** zip"文件夹，然后单击"**全部提取"。**
    
3. 单击 **"** 浏览"，选择要保存示例的位置，然后单击"提取 **"。**
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**
    
6. 浏览到保存示例的位置，单击 **"为"。单击"为 VCP.vcproj"，** 然后单击"打开 **"。**
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
9. 在保存示例的文件夹中，右键单击 **install.bat文件，** 然后单击"以 **管理员角色运行"。**
    
10. 在“用户帐户控制”对话框中，单击“继续”。
    
    > [!NOTE]
    > **Install.bat** 将.dll复制到默认Microsoft Office文件夹 C：\Program Files\Microsoft Office\Office12\. If you have installed Office products in a different location， right-click **Install.bat** and click **Edit**. 文件将在记事本。 将默认安装路径替换为计算机上使用的安装路径。 
  

