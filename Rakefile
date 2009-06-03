require 'rake'
require 'rake/clean'
require 'agent_xmpp'
require 'lib/agent_linux'

####------------------------------------------------------------------------------------------------------
namespace :db do
  desc "create database tables"
  task :migrate do
    require 'datamapper'
    require 'config/performance_monitors'
    AgentXmpp::Boot.load('app/models')
    DataMapper.setup(:default, "sqlite3://#{AgentXmpp::Boot.app_dir}/db/agent_linux.db")
    DataMapper.auto_migrate!  
  end
end

