---
title: 表单配置文件 [平台] 部分
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3b9b3dc0-4f82-468b-8e77-0374c5b196f4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7439de5b91cefe89eba2f9395595d4a7c8ca3ec5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419126"
---
# <a name="form-configuration-file-platforms-section"></a><span data-ttu-id="8f0f4-103">表单配置文件 [平台] 部分</span><span class="sxs-lookup"><span data-stu-id="8f0f4-103">Form Configuration File [Platforms] Section</span></span>

<span data-ttu-id="8f0f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8f0f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8f0f4-105">**[平台]** 一节列出了此窗体支持的完整平台集。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-105">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="8f0f4-106">每个平台条目都包含前缀**平台。**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-106">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="8f0f4-107">_字符串_, 其中_字符串_是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-107">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="8f0f4-108">每个字符串对应于单个 **[平台]** 部分的**CPU**项。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-108">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="8f0f4-109">**[平台]** 部分中的每个条目都定义了一个_平台字符串_, 该字符串引用后续的 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-109">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="8f0f4-110">_平台字符串_\*\*\*\* "一节, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-110">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="8f0f4-111">**[平台]** 一节列出了此窗体支持的完整平台集。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-111">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="8f0f4-112">每个平台条目都包含前缀**平台。**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-112">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="8f0f4-113">_字符串_, 其中_字符串_是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-113">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="8f0f4-114">每个字符串对应于单个 **[平台]** 部分的**CPU**项。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-114">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="8f0f4-115">**[平台]** 部分中的每个条目都定义了一个_平台字符串_, 该字符串引用后续的 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-115">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="8f0f4-116">_平台字符串_\*\*\*\* "一节, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-116">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="8f0f4-117">**平台**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-117">**[Platforms]**</span></span>
  
<span data-ttu-id="8f0f4-118">**平台**。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-118">**Platform**.</span></span> <span data-ttu-id="8f0f4-119">_字符串_ =  _平台字符串_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-119">_string_ =  _platform string_</span></span>
  
<span data-ttu-id="8f0f4-120">下面是 **[平台]** 部分的一个示例。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-120">Following is an example of a **[Platforms]** section.</span></span> 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

<span data-ttu-id="8f0f4-121">每个 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-121">Each **[Platform.**</span></span> <span data-ttu-id="8f0f4-122">_平台字符串_**]** 部分包含两个必需的条目: **CPU**和**OSVersion**。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-122">_platform string_ **]** section contains the two required entries, **CPU** and **OSVersion**.</span></span> <span data-ttu-id="8f0f4-123">**CPU**条目指定处理器, **OSVersion**项指定操作系统。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-123">The **CPU** entry specifies the processor, and the **OSVersion** entry specifies the operating system.</span></span> <span data-ttu-id="8f0f4-124">有效的**CPU**值如下表所述。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-124">Valid **CPU** values are described in the following table.</span></span> 
  
|<span data-ttu-id="8f0f4-125">**CPU 条目**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-125">**CPU Entry**</span></span>|<span data-ttu-id="8f0f4-126">**处理器**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-126">**Processor**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f0f4-127">Ix86</span><span class="sxs-lookup"><span data-stu-id="8f0f4-127">Ix86</span></span>  <br/> |<span data-ttu-id="8f0f4-128">Intel 80x86 和奔腾系列处理器, 以及来自 AMD、Cyrix、NextGen 和其他制造商的等效处理器。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-128">Intel 80x86 and Pentium series processors, as well as equivalent processors from AMD, Cyrix, NextGen and other manufacturers.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-129">mip</span><span class="sxs-lookup"><span data-stu-id="8f0f4-129">MIPS</span></span>  <br/> |<span data-ttu-id="8f0f4-130">MIPS R4000 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-130">MIPS R4000 series processors.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-131">AXP</span><span class="sxs-lookup"><span data-stu-id="8f0f4-131">AXP</span></span>  <br/> |<span data-ttu-id="8f0f4-132">数字设备公司 Alpha AXP 处理器。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-132">Digital Equipment Corporation Alpha AXP processor.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-133">PPC</span><span class="sxs-lookup"><span data-stu-id="8f0f4-133">PPC</span></span>  <br/> |<span data-ttu-id="8f0f4-134">Motorola 电源 PC 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-134">Motorola Power PC series processors.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-135">M68</span><span class="sxs-lookup"><span data-stu-id="8f0f4-135">M68</span></span>  <br/> |<span data-ttu-id="8f0f4-136">Mororola 68x00 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-136">Mororola 68x00 series processors.</span></span>  <br/> |
   
<span data-ttu-id="8f0f4-137">有效的**OSVersion**值如下表所述。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-137">Valid **OSVersion** values are described in the following table.</span></span> 
  
|<span data-ttu-id="8f0f4-138">**OSVersion 条目**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-138">**OSVersion Entry**</span></span>|<span data-ttu-id="8f0f4-139">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-139">**Operating System**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f0f4-140">win 3。1</span><span class="sxs-lookup"><span data-stu-id="8f0f4-140">Win3.1</span></span>  <br/> |<span data-ttu-id="8f0f4-141">windows 3.1 和 windows for 工作组3.11。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-141">Windows 3.1 and Windows for Workgroups 3.11.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-142">winnt 3。5</span><span class="sxs-lookup"><span data-stu-id="8f0f4-142">WinNT3.5</span></span>  <br/> |<span data-ttu-id="8f0f4-143">Windows NT 3.5 或更低。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-143">Windows NT 3.5 or lower.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-144">Win95</span><span class="sxs-lookup"><span data-stu-id="8f0f4-144">Win95</span></span>  <br/> |<span data-ttu-id="8f0f4-145">Windows 95。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-145">Windows 95.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-146">winnt 4。0</span><span class="sxs-lookup"><span data-stu-id="8f0f4-146">WinNT4.0</span></span>  <br/> |<span data-ttu-id="8f0f4-147">Windows NT 4.0。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-147">Windows NT 4.0.</span></span>  <br/> |
|<span data-ttu-id="8f0f4-148">Mac7</span><span class="sxs-lookup"><span data-stu-id="8f0f4-148">Mac7</span></span>  <br/> |<span data-ttu-id="8f0f4-149">Macintosh 系统7。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-149">Macintosh System 7.</span></span>  <br/> |
   
<span data-ttu-id="8f0f4-150">此外, **[Platform.**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-150">Additionally, the **[Platform.**</span></span> <span data-ttu-id="8f0f4-151">_平台字符串_\*\*\*\* "部分必须包含**File**或**LinkTo**条目。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-151">_platform string_ **]** section must contain either a **File** or **LinkTo** entry.</span></span> <span data-ttu-id="8f0f4-152">**文件**条目列出表单服务器应用程序可执行文件, 表单库在启动该表单时维护并将其加载到磁盘缓存中的新子目录中。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-152">The **File** entry lists the form server application executable file that the form library maintains and loads into a new subdirectory in the disk cache when the form is launched.</span></span> <span data-ttu-id="8f0f4-153">如果改为使用**LinkTo**条目, 则它包含从中提取**文件**信息的不同平台字符串的名称。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-153">If a **LinkTo** entry is used instead, it contains the name of a different platform string from which the **File** information is taken.</span></span> <span data-ttu-id="8f0f4-154">如果一个版本的表单支持多个平台, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-154">This is useful if one version of a form supports multiple platforms.</span></span> 
  
<span data-ttu-id="8f0f4-155">每次使用该**文件**项时, 都会使用**注册表**项, 它标识存储表单服务器应用程序的可执行文件的表单库的注册表项。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-155">The **Registry** entry is used whenever the **File** entry is used, it identifies the registry key for the form library where the executable file for the form server application is stored.</span></span> <span data-ttu-id="8f0f4-156">前面加反斜杠 (\) 的字符串放置在注册表的根目录中。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-156">Strings preceded by a backslash ( \ ) are placed at the root of the registry.</span></span> <span data-ttu-id="8f0f4-157">不以反斜杠开头的字符串放置在 HKEY_CLASSES_ROOT\CLSID\ _guid_\ 注册表项中, 其中_guid_是表单的**guid** 。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-157">Strings not preceded by a backslash are placed in the HKEY_CLASSES_ROOT\CLSID\  _GUID_\ registry key, where  _GUID_ is the **GUID** of the form.</span></span> <span data-ttu-id="8f0f4-158">字符 "% d" 可用于指示从中读取表单配置文件的目录的路径名。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-158">The characters "%d" can be used to indicate the pathname of the directory from which the form configuration file has been read.</span></span> <span data-ttu-id="8f0f4-159">这适用于指定具有相对于表单配置文件的路径名的其他文件。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-159">This is useful for specifying other files with pathnames relative to the form configuration file.</span></span> <span data-ttu-id="8f0f4-160">可以使用文件或注册表以前缀后跟任何其他文本的形式指定**多个文件**或**注册表**项。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-160">**Multiple File** or **Registry** entries can be specified by using File or Registry as a prefix followed by any other text.</span></span> <span data-ttu-id="8f0f4-161">**[平台**] 的格式。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-161">The format for the **[Platform.**</span></span> <span data-ttu-id="8f0f4-162">_平台字符串_**]** 部分为:</span><span class="sxs-lookup"><span data-stu-id="8f0f4-162">_platform string_ **]** section is:</span></span> 
  
- <span data-ttu-id="8f0f4-163">**平台.**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-163">**[Platform.**</span></span> <span data-ttu-id="8f0f4-164">_平台字符串_**]**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-164">_platform string_ **]**</span></span>
    
- <span data-ttu-id="8f0f4-165">**CPU** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-165">**CPU** =  _string_</span></span>
    
- <span data-ttu-id="8f0f4-166">**OSVersion** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-166">**OSVersion** =  _string_</span></span>
    
- <span data-ttu-id="8f0f4-167">**文件** =  _路径_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-167">**File** =  _path_</span></span>
    
- <span data-ttu-id="8f0f4-168">**LinkTo** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-168">**LinkTo** =  _string_</span></span>
    
- <span data-ttu-id="8f0f4-169">**注册表** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="8f0f4-169">**Registry** =  _string_</span></span>
  
<span data-ttu-id="8f0f4-170">以下是两个示例 **[Platform.**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-170">The following are two example **[Platform.**</span></span> <span data-ttu-id="8f0f4-171">_平台字符串_**]** 部分, 一种是使用**文件**项, 另一种是使用**LinkTo**项。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-171">_platform string_ **]** sections, one using the **File** entry and one using the **LinkTo** entry.</span></span> 
  
```cpp
[Platform.NTx86]
CPU = ix86
OSVersion = WinNT3.5
File = \helpdesk.exe
Registry = Local Server = %d\helpdesk.exe
[Platform.Win95]
CPU = ix86
OSVersion = Win95
LinkTo = NTx86

```

<span data-ttu-id="8f0f4-172">**[Platform.**</span><span class="sxs-lookup"><span data-stu-id="8f0f4-172">The **[Platform.**</span></span> <span data-ttu-id="8f0f4-173">_平台字符串_**]** 在将表单添加到本地表单库时, 将忽略该部分, 假定安装程序已将邮件类处理程序中的文件 constituting 为在 OLE 注册表中的处理程序部分中命名的可用本地存储, 并已完成系统注册表中的 OLE 注册。</span><span class="sxs-lookup"><span data-stu-id="8f0f4-173">_platform string_ **]** section is ignored when adding a form to the local form library, when it is assumed that the installer has placed the files constituting the message class handler into available local storage as named in the handler's section in the OLE registry, and has done the OLE registration in the system's registry.</span></span> 
  

