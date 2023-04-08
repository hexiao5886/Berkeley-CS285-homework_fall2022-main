BC Run:
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v4 --exp_name bc_ant --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v4.pkl --video_log_freq -1

DAgger Run:
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v4 --exp_name dagger_ant --n_iter 10 --do_dagger --expert_data cs285/expert_data/expert_data_Ant-v4.pkl --video_log_freq -1



Only complete the code, but not accomplish the experiments.

tensorboard --logdir=data/ --host localhost --port 8888

如何撤回commit？实际上会修改本地文件/删除添加到commit的文件
git reflog 找到相应commit的编号.
git revert "编号”