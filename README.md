const FORBIDDEN_USERNAMES_REGEXPS = 
  'page-not-found', 'terms-of-use', 'pricing', 'privacy-policy', 'customers',
  'request-form', 'request-solution', 'release-notes','api-reference', 'video-tutorials',
  'acts', 'schedules', 'account', 'sign-up', 'sign-in-discourse', 'admin',
  'documentation', 'change-password', 'enroll-account', 'forgot-password', 'reset-password',
  'sign-in', 'verify-email', 'live-status', 'browser-info','health-check', 'api',
  'change-log', 'dashboard'
    
    // Various strings
  'admin', 'administration', 'act', 'library', 'lib','team',
  'contact', 'documentation', 'for-business', 'for-developers', 'developers', 'business',
  'integrations', 'job', 'setting', 'settings', 'privacy', 'policy', 'assets', 'help',
  'config', 'configuration', 'terms', 'hiring', 'hire', 'status', 'status-page', 'solutions',
  'support', 'market', 'marketplace', 'download', 'downloads', 'username', 'users', 'user',
  'login', 'logout', 'signin', 'sign', 'signup', 'sign-out', 'signout', 'plugins', 'plug-ins',
  'reset', 'password', 'passwords','profile-photos', 'profiles', 'true', 'false',
  'images', 'image','app', 'schedules', 'community', 'storage', 'storages', 'account', 'video', 'knowledgebase', 
  'forum', 'customers','health-check', 'health',  'scheduler', 'api', 'sdk', 'cookies', 'cookie-policy', 
  'cookies-policy'

    // Reserved usernames from https://github.com/shouldbee/reserved-usernames/blob/master/reserved-usernames.json
  'access', 'account', 'accounts', 'activate', 'activities', 'activity', 'ad', 'add',
  'address', 'admin', 'administration', 'administrator', 'ads','advertising',
  'affiliate', 'affiliates','analysis', 'analytics', 'android',  'anonymous', 
  'api', 'app', 'apps', 'archive', 'archives','auth', 'authentication','backup','banner', 'banners', 
  'billing', 'bug', 'business','cache','call', 'campaign', 'cancel', 'captcha', 'career', 'careers',
  'cart', 'categories', 'category', 'changelog', 'chat', 'check', 'checking',
  'checkout', 'client', 'clients', 'code', 'codereview', 'comercial', 'comment',
  'comments', 'communities', 'community', 'company', 'compare','config', 'configuration',
  'connect', 'contact', 'contact-us', 'contact_us', 'contactus', 
  'create','dashboard', 'data','default', 'delete', 'demo', 'design', 'designer',
  'dev', 'devel', 'developer', 'developers','direct_messages', 'directory','documentation', 'domain',
  'download', 'downloads', 'ecommerce','email', 'employment',
  'enterprise', 'entries', 'entry', 'error', 'errors', 'eval', 'event', 'exit', 'faq', 'favorite', 'favorites', 
  'feature', 'features', 'feed', 'feedback','feeds', 'file', 'files','fleet', 'fleets','forgot', 
  'form', 'forum', 'forums',  'github',  'help',homepage', 'host', 'hosting','hostname', 'info', 'information', 
  'inquiry','invitations', 'invite','issue', 'issues', 'language', 'languages','legal', 'license',
    'link', 'links', 'linux', 'list', 'lists', 'log', 'log-in', 'log-out', 'log_in', 'log_out',
    'login', 'logout', 'logs','mail', 
    'maintenance', 'manager', 'manual', 'map', 'maps', 'marketing', 'master',
   'member', 'members', 'message', 'messages','notification', 'notifications', 'notify','null', 'oauth',
    'oauth_clients', 'offer', 'offers', 'official','online', 'openid', 'organization', 'organizations', 
    'owner', 'owners','password', 'payment',  'policy', 'privacy', 'privacy-policy', 'privacy_policy',
    'privacypolicy', 'private', 'product', 'products', 'profile', 'project', 'projects', 'promo',
   'public', 'purpose','python', 'query', 'random', 'ranking', 'read', 'readme','register', 'registration', 
   'release', 'remove', 'replies',
  'report', 'reports', 'repositories', 'repository','request', 'requests', 'reset','secure', 'security', 
  'self', 'send', 'server', 'server-info',
    'server-status', 'service', 'services', 'session', 'sessions', 'setting', 'settings', 'setup',
    'share','sign-in', 'sign-up', 'sign_in', 'sign_up', 'signin', 'signout', 'signup',
    'stats', 'status','subscribe', 'subscriptions',
    'support', 'system','term', 'terms',
    'terms-of-service', 'terms_of_service', 'termsofservice', 'test', 'test1', 'test2', 'test3',
    'teste', 'testing', 'tests','tutorial','unfollow', 'unsubscribe', 'update', 'upload', 'uploads', 'url',
   'user', 'username', 'users','version', 'yourdomain', 'yourname',
    'yoursite', 'yourusername','email','password',
    'Firmware', 'Software', 'OTA', 'guides', 'fordpass','lincoln way','lincolnway', 'update', 'upgrade'
];

// Regex matching forbidden usernames.
const FORBIDDEN_REGEXP = new RegExp(`^(${ANONYMOUS_USERNAME}|${FORBIDDEN_USERNAMES_REGEXPS.join('|')})$`, 'i');

/**
 * Checks whether username is listed in FORBIDDEN_USERNAMES
 * or matches any root route path.
 */
export function isForbiddenUsername(username: string): boolean {
  return !!username.match(FORBIDDEN_REGEXP);
}
