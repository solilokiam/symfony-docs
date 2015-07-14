Creating a custom Access Decision Strategy
==========================================

The standard :class:`Symfony\\Component\\Security\\Core\\Authorization\\AccessDecisionManagerInterface` has several
default strategies:

affirmative
consensus
unanimous

Sometimes it is useful to create your own strategy to handel a specific case that is not handled by the framework. In
this section, you'll learn how to create your own access decision strategy.

The AccessDecisionStrategyInteface
----------------------------------

A custom access decision strategy must implement
:class:`Symfony\\Component\\Security\\Core\\Authorization\\AccessDecisionStrategyInterface`, which requires the
following methods:

..code_block:: php
    interface AccessDecisionStrategyInterface
    {
        public function setVoters(array $voters);
        public function setAllowIfAllAbstainDecisions($allowIfAllAbstainDecisions);
        public function setAllowIfEqualGrantedDeniedDecisions($allowIfEqualGrantedDeniedDecisions);
        public function decide(TokenInterface $token, array $attributes, $object = null);
    }

