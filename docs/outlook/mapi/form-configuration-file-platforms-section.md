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
# <a name="form-configuration-file-platforms-section"></a><span data-ttu-id="e68c6-103">表单配置文件 [平台] 部分</span><span class="sxs-lookup"><span data-stu-id="e68c6-103">Form Configuration File [Platforms] Section</span></span>

<span data-ttu-id="e68c6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e68c6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e68c6-105">**[平台]** 部分列出了此表单支持的完整平台集。</span><span class="sxs-lookup"><span data-stu-id="e68c6-105">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="e68c6-106">每个平台条目由前缀 **Platform 组成。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-106">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="e68c6-107">_string_，其中  _string_ 是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="e68c6-107">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="e68c6-108">每个字符串对应于单个 [**平台]** 节的 **CPU** 条目。</span><span class="sxs-lookup"><span data-stu-id="e68c6-108">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="e68c6-109">**[Platforms] 节中** 的每个条目都定义一个 _引用_ 后续 **[Platform] 的平台字符串。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-109">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="e68c6-110">_platform string_ **]** 部分，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e68c6-110">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="e68c6-111">**[平台]** 部分列出了此表单支持的完整平台集。</span><span class="sxs-lookup"><span data-stu-id="e68c6-111">The **[Platforms]** section lists the complete set of platforms supported by this form.</span></span> <span data-ttu-id="e68c6-112">每个平台条目由前缀 **Platform 组成。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-112">Each platform entry consists of the prefix **Platform.**</span></span> <span data-ttu-id="e68c6-113">_string_，其中  _string_ 是平台的任意字符串代码。</span><span class="sxs-lookup"><span data-stu-id="e68c6-113">_string_, where  _string_ is an arbitrary string code for the platform.</span></span> <span data-ttu-id="e68c6-114">每个字符串对应于单个 [**平台]** 节的 **CPU** 条目。</span><span class="sxs-lookup"><span data-stu-id="e68c6-114">Each string corresponds to the **CPU** entry of an individual **[Platforms]** sections.</span></span> <span data-ttu-id="e68c6-115">**[Platforms] 节中** 的每个条目都定义一个 _引用_ 后续 **[Platform] 的平台字符串。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-115">Each entry in a **[Platforms]** section defines a  _platform string_ that references a subsequent **[Platform.**</span></span> <span data-ttu-id="e68c6-116">_platform string_ **]** 部分，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e68c6-116">_platform string_ **]** section as shown here.</span></span> 
  
<span data-ttu-id="e68c6-117">**[平台]**</span><span class="sxs-lookup"><span data-stu-id="e68c6-117">**[Platforms]**</span></span>
  
<span data-ttu-id="e68c6-118">**平台**。</span><span class="sxs-lookup"><span data-stu-id="e68c6-118">**Platform**.</span></span> <span data-ttu-id="e68c6-119">_string_  =  _平台字符串_</span><span class="sxs-lookup"><span data-stu-id="e68c6-119">_string_ =  _platform string_</span></span>
  
<span data-ttu-id="e68c6-120">下面是 **[Platforms] 部分** 的示例。</span><span class="sxs-lookup"><span data-stu-id="e68c6-120">Following is an example of a **[Platforms]** section.</span></span> 
  
```cpp
[Platforms]
Platform.1 = NTx86
Platform.2 = Win95

```

<span data-ttu-id="e68c6-121">每个 **[平台。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-121">Each **[Platform.**</span></span> <span data-ttu-id="e68c6-122">_platform string_ **]** section contains the two required entries， **CPU** and **OSVersion**.</span><span class="sxs-lookup"><span data-stu-id="e68c6-122">_platform string_ **]** section contains the two required entries, **CPU** and **OSVersion**.</span></span> <span data-ttu-id="e68c6-123">**CPU** 条目指定处理器，**而 OSVersion** 条目指定操作系统。</span><span class="sxs-lookup"><span data-stu-id="e68c6-123">The **CPU** entry specifies the processor, and the **OSVersion** entry specifies the operating system.</span></span> <span data-ttu-id="e68c6-124">下表介绍了有效的 **CPU** 值。</span><span class="sxs-lookup"><span data-stu-id="e68c6-124">Valid **CPU** values are described in the following table.</span></span> 
  
|<span data-ttu-id="e68c6-125">**CPU 条目**</span><span class="sxs-lookup"><span data-stu-id="e68c6-125">**CPU Entry**</span></span>|<span data-ttu-id="e68c6-126">**处理器**</span><span class="sxs-lookup"><span data-stu-id="e68c6-126">**Processor**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e68c6-127">Ix86</span><span class="sxs-lookup"><span data-stu-id="e68c6-127">Ix86</span></span>  <br/> |<span data-ttu-id="e68c6-128">Intel 80x86 和 Pentium 系列处理器，以及 AMD、Cyrix、NextGen 和其他制造商的等效处理器。</span><span class="sxs-lookup"><span data-stu-id="e68c6-128">Intel 80x86 and Pentium series processors, as well as equivalent processors from AMD, Cyrix, NextGen and other manufacturers.</span></span>  <br/> |
|<span data-ttu-id="e68c6-129">MIPS</span><span class="sxs-lookup"><span data-stu-id="e68c6-129">MIPS</span></span>  <br/> |<span data-ttu-id="e68c6-130">MIPS R4000 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="e68c6-130">MIPS R4000 series processors.</span></span>  <br/> |
|<span data-ttu-id="e68c6-131">AXP</span><span class="sxs-lookup"><span data-stu-id="e68c6-131">AXP</span></span>  <br/> |<span data-ttu-id="e68c6-132">数字设备公司 Alpha AXP 处理器。</span><span class="sxs-lookup"><span data-stu-id="e68c6-132">Digital Equipment Corporation Alpha AXP processor.</span></span>  <br/> |
|<span data-ttu-id="e68c6-133">PPC</span><span class="sxs-lookup"><span data-stu-id="e68c6-133">PPC</span></span>  <br/> |<span data-ttu-id="e68c6-134">Motorola Power PC 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="e68c6-134">Motorola Power PC series processors.</span></span>  <br/> |
|<span data-ttu-id="e68c6-135">M68</span><span class="sxs-lookup"><span data-stu-id="e68c6-135">M68</span></span>  <br/> |<span data-ttu-id="e68c6-136">Mororola 68x00 系列处理器。</span><span class="sxs-lookup"><span data-stu-id="e68c6-136">Mororola 68x00 series processors.</span></span>  <br/> |
   
<span data-ttu-id="e68c6-137">下表介绍了有效的 **OSVersion** 值。</span><span class="sxs-lookup"><span data-stu-id="e68c6-137">Valid **OSVersion** values are described in the following table.</span></span> 
  
|<span data-ttu-id="e68c6-138">**OSVersion 条目**</span><span class="sxs-lookup"><span data-stu-id="e68c6-138">**OSVersion Entry**</span></span>|<span data-ttu-id="e68c6-139">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="e68c6-139">**Operating System**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e68c6-140">Win3.1</span><span class="sxs-lookup"><span data-stu-id="e68c6-140">Win3.1</span></span>  <br/> |<span data-ttu-id="e68c6-141">Windows工作组 3.11 Windows 3.1 和 3.11。</span><span class="sxs-lookup"><span data-stu-id="e68c6-141">Windows 3.1 and Windows for Workgroups 3.11.</span></span>  <br/> |
|<span data-ttu-id="e68c6-142">WinNT3.5</span><span class="sxs-lookup"><span data-stu-id="e68c6-142">WinNT3.5</span></span>  <br/> |<span data-ttu-id="e68c6-143">Windows NT 3.5 或更低。</span><span class="sxs-lookup"><span data-stu-id="e68c6-143">Windows NT 3.5 or lower.</span></span>  <br/> |
|<span data-ttu-id="e68c6-144">Win95</span><span class="sxs-lookup"><span data-stu-id="e68c6-144">Win95</span></span>  <br/> |<span data-ttu-id="e68c6-145">Windows 95.</span><span class="sxs-lookup"><span data-stu-id="e68c6-145">Windows 95.</span></span>  <br/> |
|<span data-ttu-id="e68c6-146">WinNT4.0</span><span class="sxs-lookup"><span data-stu-id="e68c6-146">WinNT4.0</span></span>  <br/> |<span data-ttu-id="e68c6-147">Windows NT 4.0 版。</span><span class="sxs-lookup"><span data-stu-id="e68c6-147">Windows NT 4.0.</span></span>  <br/> |
|<span data-ttu-id="e68c6-148">Mac7</span><span class="sxs-lookup"><span data-stu-id="e68c6-148">Mac7</span></span>  <br/> |<span data-ttu-id="e68c6-149">Macintosh 系统 7。</span><span class="sxs-lookup"><span data-stu-id="e68c6-149">Macintosh System 7.</span></span>  <br/> |
   
<span data-ttu-id="e68c6-150">此外 **，[Platform.**</span><span class="sxs-lookup"><span data-stu-id="e68c6-150">Additionally, the **[Platform.**</span></span> <span data-ttu-id="e68c6-151">_platform string_ **]** section must contain either a **File** or **LinkTo** entry.</span><span class="sxs-lookup"><span data-stu-id="e68c6-151">_platform string_ **]** section must contain either a **File** or **LinkTo** entry.</span></span> <span data-ttu-id="e68c6-152">" **文件** "条目列出了表单库维护的表单服务器应用程序可执行文件，并加载在启动表单时磁盘缓存中的新子目录中。</span><span class="sxs-lookup"><span data-stu-id="e68c6-152">The **File** entry lists the form server application executable file that the form library maintains and loads into a new subdirectory in the disk cache when the form is launched.</span></span> <span data-ttu-id="e68c6-153">如果 **改为使用 LinkTo** 条目，则它包含从其中获取文件信息的不同 **平台字符串** 的名称。</span><span class="sxs-lookup"><span data-stu-id="e68c6-153">If a **LinkTo** entry is used instead, it contains the name of a different platform string from which the **File** information is taken.</span></span> <span data-ttu-id="e68c6-154">如果表单的一个版本支持多个平台，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="e68c6-154">This is useful if one version of a form supports multiple platforms.</span></span> 
  
<span data-ttu-id="e68c6-155">每当 **使用**"文件"项时，都会使用注册表项，它标识存储表单服务器应用程序的可执行文件的表单库的注册表项。</span><span class="sxs-lookup"><span data-stu-id="e68c6-155">The **Registry** entry is used whenever the **File** entry is used, it identifies the registry key for the form library where the executable file for the form server application is stored.</span></span> <span data-ttu-id="e68c6-156">前面带有反 ( \ ) 的字符串位于注册表的根目录下。</span><span class="sxs-lookup"><span data-stu-id="e68c6-156">Strings preceded by a backslash ( \ ) are placed at the root of the registry.</span></span> <span data-ttu-id="e68c6-157">前面没有反杠的字符串放置在 guiD \ 注册表HKEY_CLASSES_ROOT\CLSID\ _GUID_\注册表项中，其中 _GUID_ 是表单 **的 GUID。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-157">Strings not preceded by a backslash are placed in the HKEY_CLASSES_ROOT\CLSID\  _GUID_\ registry key, where  _GUID_ is the **GUID** of the form.</span></span> <span data-ttu-id="e68c6-158">字符"%d"可用于指示已读取表单配置文件的目录的路径名。</span><span class="sxs-lookup"><span data-stu-id="e68c6-158">The characters "%d" can be used to indicate the pathname of the directory from which the form configuration file has been read.</span></span> <span data-ttu-id="e68c6-159">这可用于指定具有相对于表单配置文件的路径名的其他文件。</span><span class="sxs-lookup"><span data-stu-id="e68c6-159">This is useful for specifying other files with pathnames relative to the form configuration file.</span></span> <span data-ttu-id="e68c6-160">**可以使用 File** **或 Registry** 作为前缀，后跟任何其他文本来指定多个 File 或 Registry 项。</span><span class="sxs-lookup"><span data-stu-id="e68c6-160">**Multiple File** or **Registry** entries can be specified by using File or Registry as a prefix followed by any other text.</span></span> <span data-ttu-id="e68c6-161">**[Platform.**</span><span class="sxs-lookup"><span data-stu-id="e68c6-161">The format for the **[Platform.**</span></span> <span data-ttu-id="e68c6-162">_platform string_ **]** section is：</span><span class="sxs-lookup"><span data-stu-id="e68c6-162">_platform string_ **]** section is:</span></span> 
  
- <span data-ttu-id="e68c6-163">**[平台。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-163">**[Platform.**</span></span> <span data-ttu-id="e68c6-164">_platform string_ **]**</span><span class="sxs-lookup"><span data-stu-id="e68c6-164">_platform string_ **]**</span></span>
    
- <span data-ttu-id="e68c6-165">**CPU**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e68c6-165">**CPU** =  _string_</span></span>
    
- <span data-ttu-id="e68c6-166">**OSVersion**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e68c6-166">**OSVersion** =  _string_</span></span>
    
- <span data-ttu-id="e68c6-167">**文件**  =  _path_</span><span class="sxs-lookup"><span data-stu-id="e68c6-167">**File** =  _path_</span></span>
    
- <span data-ttu-id="e68c6-168">**LinkTo**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e68c6-168">**LinkTo** =  _string_</span></span>
    
- <span data-ttu-id="e68c6-169">**注册表**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="e68c6-169">**Registry** =  _string_</span></span>
  
<span data-ttu-id="e68c6-170">下面是两个示例 **[Platform。**</span><span class="sxs-lookup"><span data-stu-id="e68c6-170">The following are two example **[Platform.**</span></span> <span data-ttu-id="e68c6-171">_platform string_ **]** sections， one using the **File** entry and one using the **LinkTo** entry.</span><span class="sxs-lookup"><span data-stu-id="e68c6-171">_platform string_ **]** sections, one using the **File** entry and one using the **LinkTo** entry.</span></span> 
  
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

<span data-ttu-id="e68c6-172">**[Platform.**</span><span class="sxs-lookup"><span data-stu-id="e68c6-172">The **[Platform.**</span></span> <span data-ttu-id="e68c6-173">_当_ 将表单添加到本地表单库时，如果假定安装程序将包含邮件类处理程序的文件放置到 OLE 注册表中处理程序部分命名的可用本地存储中，并且已完成系统注册表中的 OLE 注册，则忽略 platform string **]** 节。</span><span class="sxs-lookup"><span data-stu-id="e68c6-173">_platform string_ **]** section is ignored when adding a form to the local form library, when it is assumed that the installer has placed the files constituting the message class handler into available local storage as named in the handler's section in the OLE registry, and has done the OLE registration in the system's registry.</span></span> 
  

