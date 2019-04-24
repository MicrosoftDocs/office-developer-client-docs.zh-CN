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
  
此示例支持从简单二进制文件读取的显示名称和电子邮件地址的单个只读容器。 该示例支持一次性模板和除配置文件向导之外的所有配置选项。
  
您可以从[Outlook 消息处理 API (MAPI) 代码示例](https://go.microsoft.com/fwlink/?LinkId=129740
)中下载此示例。
  
|||
|:-----|:-----|
|执行  <br/> |SABP32  <br/> |
| 源代码目录:  <br/> |SampleAddressBookProvider\SABP  <br/> |
|语言  <br/> |c  <br/> |
|平台  <br/> |Microsoft Visual Studio 2008 for windows Vista、windows server 2008、windows XP SP2 和 windows Server 2003 SP1 的编译  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能:
  
- 表限制。 此示例实现前缀匹配和不明确名称解析。 它不实现完全 MAPI 限制语言, 并且仅对显示名称支持限制。
    
- 消息用户的详细信息显示表。 
    
- 一次性地址。
    
- "高级搜索" 对话框。
    
- [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 此接口部分受支持;它的**IMAPIProp**方法将委派给**IPropData**接口。 有关详细信息, 请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md) interface。 
    
- 交互式和编程配置。
    
## <a name="unsupported-features"></a>不支持的功能

此示例不支持以下功能:
  
- 筛选.
    
- 通讯组列表。
    
- 创建、删除和修改项。
    
- 具有多个值的属性。
    
- 命名属性。
    
- 区分显示名称中的名字和姓氏。
    
 **安装示例通讯簿提供程序**
  
1. 若要下载示例通讯簿提供程序, 请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 Outlook MAPI 示例的文件夹。 右键单击 " **OutlookMAPISamples\<\>号码**" zip 文件夹, 然后单击 "**全部提取**"。
    
3. 单击 "**浏览**", 选择要保存示例的位置, 然后单击 "**提取**"。
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。
    
6. 浏览到保存示例的位置, 单击 " **SABP**", 然后单击 "**打开**"。
    
7. 在"构建"菜单上，单击"构建解决方案"。
    
8. 在 "**将文件另存为**" 对话框中, 单击 "**保存**"。
    
9. 在保存该示例的文件夹中, 右键单击该 **.bat**文件, 然后单击 "**以管理员身份运行**"。
    
10. 在“用户帐户控制”**** 对话框中，单击“继续”****。
    
    > [!NOTE]
    > **.bat**将 .dll 复制到默认的 Microsoft Office 安装文件夹中, C:\Program Files\Microsoft Office\Office12\. 如果您已将 Office 产品安装在其他位置, 请右键单击 " **Install** ", 然后单击 "**编辑**"。 文件将在记事本中打开。 将默认安装路径替换为计算机上使用的安装路径。 
  

