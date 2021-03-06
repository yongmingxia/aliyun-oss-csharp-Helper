# Aliyun-Oss-CSharp-Helper

阿里云 OSS .Net SDK 再次封装

这里的再次封装主要是为了使用方便，官方给的文档太分散。

<h2>函数列表</h2>
<li>bool CreateBucket()</li>
<h5>创建Bucket&nbsp;&nbsp;<em>返回：</em>true-创建成功 false-创建失败</h5>
<li>CannedAccessControlList GetBucketAcl()</li>
<h5>获取Bucket访问权限 返回:CannedAccessControlList枚举类型</h5>
<li>IEnumerable<Bucket> ListBuckets()</li>
<h5>列出用户所有Bucket 返回:IEnumerable&lt;Bucket&gt;</h5>
<li>bool IsBucketExist()</li>
<h5>判断Bucket是否存在</h5>
<li>bool IsBucketExist(string bucketName)</li>
<h5>判断指定的Bucket是否存在 参数：bucketName-指定Bucket 返回：true-存在 false-不存在</h5>
<li>bool SetBucketAcl(CannedAccessControlList accessType)</li>
<h5>设置Bucket访问权限 参数：accessType-访问权限 返回：true-设置成功 false-设置失败</h5>
<li>bool SetBucketAcl()</li>
<h5>设置指定Bucket访问权限 参数：bucketName-指定Bucket accessType-访问权限 返回：true-设置成功 false-设置失败</h5>
<li>bool DeleteBucket()</li>
<h5>删除Bucket 返回：true-删除成功 false-删除失败</h5>
<li>bool DeleteBucket(string bucketName)</li>
<h5>删除指定Bucket</h5>
==============================================================
<li>bool PutString(string str,string name)</li>
<h5>上传字符串 返回：true-上传成功 false-上传失败 参数：str-字符串 name-在OSS存储用的标识(必须唯一，否则会替换)</h5>
<li>bool PutString(string bucketName,string str,string name)</li>
<h5>上传字符串 返回：true-上传成功 false-上传失败 参数：bucketName-Bucket名字 str-字符串 name-在OSS存储用的标识</h5>
<li>bool PutFile(string filePath)</li>
<h5>上传文件 返回：true-上传成功 false-上传失败 参数：filePath-要上传的文件路径</h5>
<li>bool PutFile(string filePath,string objectKey)</li>
<h5>上传文件 返回：true-上传成功 false-上传失败 参数：filePath-要上传的文件路径 objectKey-在OSS中存储用的标识</h5>
<li>bool PutFile(string bucketName,string filePath,string objectKey)</li>
<h5>上传文件 返回：true-上传成功 false-上传失败 参数：bucketName-指定Bucket filePath-要上传的文件路径 objectKey-在OSS中存储用的标识</h5>
<li>bool PutFile(string filePath,string objectKey,EventHandler<StreamTransferProgressArgs> progressCallback)</li>
<h5>上传文件并显示进度 返回：true-上传成功 false-上传失败 参数：filePath-要上传的文件路径 objectKey-在OSS中存储用的标识 progressCallback-上传进度处理函数，可参考下面的代码</h5>
<h5>上传进度事件处理函数</h5>
<pre><code>
        private static void streamProgressCallback(object sender, StreamTransferProgressArgs args)
        {
            System.Console.WriteLine("ProgressCallback - TotalBytes:{0}, TransferredBytes:{1}",
                args.TotalBytes, args.TransferredBytes);
        }
</code></pre>
<li>bool PutFile(string bucketName,string filePath,string objectKey,EventHandler<StreamTransferProgressArgs> progressCallback)</li>
<h5>上传文件并显示进度 返回：true-上传成功 false-上传失败 参数：bucketName-指定Bucket filePath-要上传的文件路径 objectKey-在OSS中存储用的标识 progressCallback-上传进度处理函数</h5>
<h2>使用示例</h2>
<h2>示例程序</h2>
提供简单的上传，下载和管理功能。示例程序只用到一些基本的函数，掌握这些基本函数，我们就已经掌握了OSS的基本使用了。如果后面有时间，会把大部分函数都用到示例程序中去。
<br/>
<h5>软件截图</h5>
<p align="center">
        <img src="https://github.com/zhaotianff/aliyun-oss-csharp-Helper/blob/master/AliyunOssHelperLib/OssDemo/ScreenShots/1.png" align="center" alt="start up"/>
        <p align="center">上传</p>
</p>
<p align="center">
        <img src="https://github.com/zhaotianff/aliyun-oss-csharp-Helper/blob/master/AliyunOssHelperLib/OssDemo/ScreenShots/2.png" align="center" alt="start up"/>
        <p align="center">下载</p>
</p>
<p align="center">
        <img src="https://github.com/zhaotianff/aliyun-oss-csharp-Helper/blob/master/AliyunOssHelperLib/OssDemo/ScreenShots/3.png" align="center" alt="start up"/>
        <p align="center">配置</p>
</p>
