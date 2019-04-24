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
# <a name="address-book-provider-sample"></a><span data-ttu-id="093da-103">通讯簿提供程序示例</span><span class="sxs-lookup"><span data-stu-id="093da-103">Address Book Provider Sample</span></span>

  
  
<span data-ttu-id="093da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="093da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="093da-105">此示例支持从简单二进制文件读取的显示名称和电子邮件地址的单个只读容器。</span><span class="sxs-lookup"><span data-stu-id="093da-105">This sample supports a single read-only container for display names and email addresses, which are read from a flat binary file.</span></span> <span data-ttu-id="093da-106">该示例支持一次性模板和除配置文件向导之外的所有配置选项。</span><span class="sxs-lookup"><span data-stu-id="093da-106">The sample supports one-off templates and all configuration options except the Profile Wizard.</span></span>
  
<span data-ttu-id="093da-107">您可以从[Outlook 消息处理 API (MAPI) 代码示例](https://go.microsoft.com/fwlink/?LinkId=129740
)中下载此示例。</span><span class="sxs-lookup"><span data-stu-id="093da-107">You can download this sample from [Outlook Messaging API (MAPI) Code Samples](https://go.microsoft.com/fwlink/?LinkId=129740
).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="093da-108">执行</span><span class="sxs-lookup"><span data-stu-id="093da-108">Executable:</span></span>  <br/> |<span data-ttu-id="093da-109">SABP32</span><span class="sxs-lookup"><span data-stu-id="093da-109">SABP32.dll</span></span>  <br/> |
| <span data-ttu-id="093da-110">源代码目录:</span><span class="sxs-lookup"><span data-stu-id="093da-110">Source code directory:</span></span>  <br/> |<span data-ttu-id="093da-111">SampleAddressBookProvider\SABP</span><span class="sxs-lookup"><span data-stu-id="093da-111">SampleAddressBookProvider\SABP</span></span>  <br/> |
|<span data-ttu-id="093da-112">语言</span><span class="sxs-lookup"><span data-stu-id="093da-112">Language:</span></span>  <br/> |<span data-ttu-id="093da-113">c</span><span class="sxs-lookup"><span data-stu-id="093da-113">C++</span></span>  <br/> |
|<span data-ttu-id="093da-114">平台</span><span class="sxs-lookup"><span data-stu-id="093da-114">Platforms:</span></span>  <br/> |<span data-ttu-id="093da-115">Microsoft Visual Studio 2008 for windows Vista、windows server 2008、windows XP SP2 和 windows Server 2003 SP1 的编译</span><span class="sxs-lookup"><span data-stu-id="093da-115">Microsoft Visual Studio 2008 to compile for Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
## <a name="supported-features"></a><span data-ttu-id="093da-116">支持的功能</span><span class="sxs-lookup"><span data-stu-id="093da-116">Supported Features</span></span>

<span data-ttu-id="093da-117">此示例支持以下功能:</span><span class="sxs-lookup"><span data-stu-id="093da-117">This sample supports the following features:</span></span>
  
- <span data-ttu-id="093da-118">表限制。</span><span class="sxs-lookup"><span data-stu-id="093da-118">Table restrictions.</span></span> <span data-ttu-id="093da-119">此示例实现前缀匹配和不明确名称解析。</span><span class="sxs-lookup"><span data-stu-id="093da-119">The sample implements prefix-match and ambiguous-name resolution.</span></span> <span data-ttu-id="093da-120">它不实现完全 MAPI 限制语言, 并且仅对显示名称支持限制。</span><span class="sxs-lookup"><span data-stu-id="093da-120">It does not implement the full MAPI restriction language, and restrictions are supported only on the display name.</span></span>
    
- <span data-ttu-id="093da-121">消息用户的详细信息显示表。</span><span class="sxs-lookup"><span data-stu-id="093da-121">A details display table for messaging users.</span></span> 
    
- <span data-ttu-id="093da-122">一次性地址。</span><span class="sxs-lookup"><span data-stu-id="093da-122">One-off addresses.</span></span>
    
- <span data-ttu-id="093da-123">"高级搜索" 对话框。</span><span class="sxs-lookup"><span data-stu-id="093da-123">An advanced search dialog box.</span></span>
    
- <span data-ttu-id="093da-124">[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="093da-124">An [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> <span data-ttu-id="093da-125">此接口部分受支持;它的**IMAPIProp**方法将委派给**IPropData**接口。</span><span class="sxs-lookup"><span data-stu-id="093da-125">This interface is partially supported; its **IMAPIProp** methods are delegated to the **IPropData** interface.</span></span> <span data-ttu-id="093da-126">有关详细信息, 请参阅[IPropData: IMAPIProp](ipropdataimapiprop.md) interface。</span><span class="sxs-lookup"><span data-stu-id="093da-126">For more information, see the [IPropData : IMAPIProp](ipropdataimapiprop.md) interface.</span></span> 
    
- <span data-ttu-id="093da-127">交互式和编程配置。</span><span class="sxs-lookup"><span data-stu-id="093da-127">Interactive and programmatic configuration.</span></span>
    
## <a name="unsupported-features"></a><span data-ttu-id="093da-128">不支持的功能</span><span class="sxs-lookup"><span data-stu-id="093da-128">Unsupported Features</span></span>

<span data-ttu-id="093da-129">此示例不支持以下功能:</span><span class="sxs-lookup"><span data-stu-id="093da-129">This sample does not support the following features:</span></span>
  
- <span data-ttu-id="093da-130">筛选.</span><span class="sxs-lookup"><span data-stu-id="093da-130">Sorting.</span></span>
    
- <span data-ttu-id="093da-131">通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="093da-131">Distribution lists.</span></span>
    
- <span data-ttu-id="093da-132">创建、删除和修改项。</span><span class="sxs-lookup"><span data-stu-id="093da-132">Creating, deleting, and modifying entries.</span></span>
    
- <span data-ttu-id="093da-133">具有多个值的属性。</span><span class="sxs-lookup"><span data-stu-id="093da-133">Properties with multiple values.</span></span>
    
- <span data-ttu-id="093da-134">命名属性。</span><span class="sxs-lookup"><span data-stu-id="093da-134">Named properties.</span></span>
    
- <span data-ttu-id="093da-135">区分显示名称中的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="093da-135">Distinguishing between first and last names in display names.</span></span>
    
 <span data-ttu-id="093da-136">**安装示例通讯簿提供程序**</span><span class="sxs-lookup"><span data-stu-id="093da-136">**To install the Sample Address Book Provider**</span></span>
  
1. <span data-ttu-id="093da-137">若要下载示例通讯簿提供程序, 请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="093da-137">To download the Sample Address Book Provider, see [Downloading the Outlook MAPI Samples](downloading-the-outlook-mapi-samples.md).</span></span>
    
2. <span data-ttu-id="093da-138">找到保存 Outlook MAPI 示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="093da-138">Locate the folder where you saved the Outlook MAPI Samples.</span></span> <span data-ttu-id="093da-139">右键单击 " **OutlookMAPISamples\<\>号码**" zip 文件夹, 然后单击 "**全部提取**"。</span><span class="sxs-lookup"><span data-stu-id="093da-139">Right-click the **OutlookMAPISamples-\<version number\>** zip folder and click **Extract All**.</span></span>
    
3. <span data-ttu-id="093da-140">单击 "**浏览**", 选择要保存示例的位置, 然后单击 "**提取**"。</span><span class="sxs-lookup"><span data-stu-id="093da-140">Click **Browse**, select the location where you want to save the sample, and click **Extract**.</span></span>
    
4. <span data-ttu-id="093da-141">运行 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="093da-141">Run Visual Studio 2008.</span></span>
    
5. <span data-ttu-id="093da-142">在 Visual Studio 2008 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="093da-142">In Visual Studio 2008, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
6. <span data-ttu-id="093da-143">浏览到保存示例的位置, 单击 " **SABP**", 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="093da-143">Browse to the location where you saved the sample, click **SABP.vcproj**, and then click **Open**.</span></span>
    
7. <span data-ttu-id="093da-144">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="093da-144">On the **Build** menu, click **Build Solution**.</span></span>
    
8. <span data-ttu-id="093da-145">在 "**将文件另存为**" 对话框中, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="093da-145">In the **Save File As** dialog box, click **Save**.</span></span>
    
9. <span data-ttu-id="093da-146">在保存该示例的文件夹中, 右键单击该 **.bat**文件, 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="093da-146">In the folder where you saved the sample, right-click the **install.bat** file and click **Run as administrator**.</span></span>
    
10. <span data-ttu-id="093da-147">在“用户帐户控制”\*\*\*\* 对话框中，单击“继续”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="093da-147">In the **User Account Control** dialog box, click **Continue**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="093da-148">**.bat**将 .dll 复制到默认的 Microsoft Office 安装文件夹中, C:\Program Files\Microsoft Office\Office12\.</span><span class="sxs-lookup"><span data-stu-id="093da-148">**Install.bat** copies the .dll to the default Microsoft Office installation folder, C:\Program Files\Microsoft Office\Office12\.</span></span> <span data-ttu-id="093da-149">如果您已将 Office 产品安装在其他位置, 请右键单击 " **Install** ", 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="093da-149">If you have installed Office products in a different location, right-click **Install.bat** and click **Edit**.</span></span> <span data-ttu-id="093da-150">文件将在记事本中打开。</span><span class="sxs-lookup"><span data-stu-id="093da-150">The file opens in Notepad.</span></span> <span data-ttu-id="093da-151">将默认安装路径替换为计算机上使用的安装路径。</span><span class="sxs-lookup"><span data-stu-id="093da-151">Replace the default installation path with the installation path used on your computer.</span></span> 
  

