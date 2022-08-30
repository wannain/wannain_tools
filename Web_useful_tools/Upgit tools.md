# How to use Upgit in Typora

[Reference Page](https://support.typora.io/Upload-Image/#configuration)

1. Download it from [Release](https://github.com/pluveto/upgit/releases).

2. Rename it to `upgit` (For Windows users, `upgit.exe`), save it to somewhere you like.

   ![image-20220830180116257](https://raw.githubusercontent.com/wannain/image/main/2022/08/upgit_20220830_1661853676.png)

3. Configure it with `~/.upgit.config.toml` or `[UPGIT_DIRECTORY]/config.toml` in following [this sample config file](https://github.com/pluveto/upgit/blob/main/config.sample.toml).

   ![image-20220830180200193](https://raw.githubusercontent.com/wannain/image/main/2022/08/upgit_20220830_1661853720.png)

```
# =============================================================================
# UPGIT Config
# =============================================================================

# default uploader id
default_uploader = "github"

# The file name formatting template is applied when uploading
#   / is directory separator used to distinguish directories
#   {year} Year, for example: 2022
#   {month} Month, for example: 02
#   {day} Day, for example: 01
#   {unix_ts} Time stamp, for example: 1643617626. If you're uploading frequently, try {unix_tsms} to escape name repeating
#   {fname} Original file name, such as logo (without suffix)
#   {fname_hash} MD5 hash value of {fname}
#   {ext} File name suffix, for example: .png
#   The following example generates a file name like: 2022/01/upgit_20220131_1643617626.png
rename = "{year}/{month}/upgit_{year}{month}{day}_{unix_ts}{ext}"

# -----------------------------------------------------------------------------
# Custom extra output formats
# -----------------------------------------------------------------------------
#   {url} direct URL of the file
[output_formats]
"bbcode" = "[img]{url}[/img]"
"html" = '<img src="{url}" />'
"markdown-simple" = "![]({url})"

# -----------------------------------------------------------------------------
# URL replacing rules. Process: RawUrl -[replace]-> Url
# -----------------------------------------------------------------------------

# If your network access to Github is abnormal or sluggish, you can try the following CDN acceleration.
# [replacements]
# "raw.githubusercontent.com" = "cdn.jsdelivr.net/gh"
# "/master" = "@master"

# =============================================================================
# Configurations examples for some uploaders, leave them blank if not used
# =============================================================================

# Github uploader
[uploaders.github]
# Branch to save files, for example master or main
branch = "master"

# "pat" enter the Github token that has the "repo" permission
# Get token from https://github.com/settings/tokens
pat = "ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

# The name of your public Github repository
# Attention: In order for you and others to access image resources, your Github repository must be public.
#            In private repositories Github blocks unauthorized requests and you will get a 404.
repo = "repo-name"

# your Github username  
username = "username"

# SMMS Uploader
[uploaders.smms]
# Get token from https://sm.ms/home/apitoken
token = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

# Imgur Uploader
[uploaders.imgur]
# Get token from https://api.imgur.com/oauth2/addclient
# See your apps in https://imgur.com/account/settings/apps
client_id = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

# Chevereto Uploader
[uploaders.chevereto]
key = "c8f8f8f8f8f8f8f8f8f8f8f8f8f8f8f8f8f8f8f8"
upload_url = "https://chevereto.com/api/v1/upload"

# Qcloudcos Uploader
[uploaders.qcloudcos]
host = "xxx.cos.ap-chengdu.myqcloud.com"
secret_id = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
secret_key= "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

# Qiniu cloud
[uploaders.qiniu]
# Generate Token: http://jsfiddle.net/gh/get/extjs/4.2/icattlecoder/jsfiddle/tree/master/uptoken
token = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx:xxxxxxxxxxxxxxxxxxxxxxxxxxx:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx=="
prefix = "https://cdn.mydomain.com/"

# Gitee
[uploaders.gitee]
username = "username"
repo = "repo-name"
# https://gitee.com/profile/personal_access_tokens/new
access_token = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

[uploaders.cloudinary]
cloud_name = "my_cloud"
upload_preset = "preset_name"

[uploaders.easyimage]
request_url = "https://img.545141.com/api/index.php"
token = "1c17b11693cb5ec63859b0ccccccccccc"
```

4. Select *File > Preferences…*

![image-20220830180343970](https://raw.githubusercontent.com/wannain/image/main/2022/08/upgit_20220830_1661853824.png)